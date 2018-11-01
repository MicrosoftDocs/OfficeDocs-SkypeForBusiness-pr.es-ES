---
title: Implementación de Lync Web App
TOCTitle: Implementación de Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48276425
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de Lync Web App

 

_**Última modificación del tema:** 2016-12-08_

Lync Web App es un cliente web de Internet Information Services (IIS) que se instala con Lync Server 2013 y está habilitado de manera predeterminada. No se necesitan pasos adicionales para habilitar Lync Web App en el servidor ni para implementar el cliente web para los usuarios. Cuando un usuario hace clic en la dirección URL de una reunión, pero no tiene instalado el cliente de Lync 2013, el usuario verá una opción para unirse a la reunión con la última versión de Lync Web App.

Las características de voz, vídeo y uso compartido de Lync Web App requieren un control Microsoft ActiveX. Puede instalar el control ActiveX previamente o permitir que los usuarios lo instalen cuando se solicite, es decir, la primera vez que usan Lync Web App o la primera vez que tienen acceso a una característica que requiere el control ActiveX.


> [!NOTE]
> En las implementaciones de servidores perimetrales Lync Server 2013, se necesita un proxy inverso HTTPS en la red perimetral para el acceso de clientes de Lync Web App. También debe publicar direcciones URL simples. Para más información, vea <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuración de los servidores proxy inversos para Lync Server 2013</A> y <A href="lync-server-2013-planning-for-simple-urls.md">Planeación de las direcciones URL simples en Lync Server 2013</A>.



## Habilitar la autenticación multifactor para Lync Web App

La versión de Lync Server 2013 de Lync Web App admite la autenticación multifactor. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unan desde redes externas al iniciar sesión en las reuniones de Lync. Para habilitar la autenticación multifactor, implemente el servidor de federación de los Servicios de federación de Active Directory (AD FS) y habilite la autenticación pasiva en Lync Server 2013. Una vez configurado AD FS, los usuarios externos que intenten unirse a reuniones de Lync verán una página web de autenticación multifactor de AD FS con el desafío de nombre de usuario y contraseña, junto con los demás métodos de autenticación adicionales que haya configurado.

> [!IMPORTANT]  
> A continuación, se incluyen algunas consideraciones importantes para planear la configuración de AD FS para la autenticación multifactor:
> <ul>
> <li><p>La autenticación multifactor de AD FS funciona si el organizador y el participante de la reunión están en la misma organización o si ambos provienen de una organización federada con AD FS. La autenticación multifactor de AD FS no funciona con los usuarios federados de Lync, porque la infraestructura web de los servidores Lync no la admite actualmente.</p></li>
> <li><p>Si usa equilibradores de carga de hardware, habilite la persistencia basada en cookies en los equilibradores de carga, para que todas las solicitudes del cliente de Lync Web App se controlen con el mismo servidor front-end.</p></li>
> <li><p>Al establecer una relación de confianza para usuario autenticado entre Lync Server y los servidores de AD FS, asigne un token con una extensión adecuada para abarcar la duración máxima de las reuniones de Lync. Por lo general, una duración de token de 240 minutos es suficiente.</p></li>
> <li><p>Esta configuración no se aplica a los clientes móviles de Lync.</p></li>
> </ul>


**Para configurar la autenticación multifactor**

1.  Instale un rol del servidor de federación de AD FS. Para más información, vea la Guía de implementación de Servicios de federación de Active Directory 2.0 en [http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0xc0a).

2.  Cree certificados para AD FS. Para obtener más información, consulte la sección “Certificados de servidor de federación” del tema Planear e implementar AD FS para su uso con el inicio de sesión único, en [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  En la Interfaz de la línea de comandos Windows PowerShell, ejecute el siguiente comando:
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Establezca una relación de usuario mediante la ejecución del siguiente comando:
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Defina las siguientes reglas de usuario de confianza:
    
```
$IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
```
```
Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
```    
```
Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
```

## Configuración de BranchCache

La característica BranchCache de Windows 7 y Windows Server 2008 R2 puede interferir con los componentes web de Lync Web App. Para evitar que los usuarios de Lync Web App tengan problemas, asegúrese de que BranchCache no esté habilitado.

Para más información sobre cómo deshabilitar BranchCache, vea la Guía de implementación de BranchCache, que está disponible en formato Word en el Centro de descarga de Microsoft, en [http://go.microsoft.com/fwlink/?linkid=268788\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268788%26clcid=0xc0a), y en formato HTML en la Biblioteca técnica de Windows Server 2008 R2, en [http://go.microsoft.com/fwlink/?linkid=268789\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268789%26clcid=0xc0a).

## Comprobar la implementación de Lync Web App

Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba puedan participar de una conferencia con la API web de comunicaciones unificadas (UCWA). Para más información sobre este cmdlet, vea [Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference) en la documentación del Shell de administración de Lync Server.

## Solucionar problemas con la instalación del complemento en Windows Server 2008 R2

Si se produce un error al instalar el complemento en un equipo que ejecuta Windows Server 2008 R2, es posible que deba modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del Registro DisableMSI.

**Para modificar la configuración de seguridad de Internet Explorer**

1.  Abra Internet Explorer.

2.  Haga clic en **Herramientas**, en **Opciones de Internet** y en **Opciones avanzadas**.

3.  Desplácese hacia abajo hasta la sección **Seguridad**.

4.  Desactive **No guardar las páginas cifradas en el disco** y haga clic en **Aceptar**.
    

    > [!NOTE]
    > Si esta opción está activada, también se generará un error al intentar descargar datos adjuntos desde Lync Web App.



5.  Vuelva a unirse a la reunión. El complemento debería descargarse sin errores.

**Para modificar la configuración del Registro DisableMSI**

1.  Haga clic en **Inicio** y en **Ejecutar**.

2.  Para tener acceso al Editor del Registro, escriba **regedit**.

3.  Navegue hasta HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.

4.  Modifique o agregue la clave del Registro DisableMSI de tipo REG\_DWORD, y defínala en 0.

5.  Vuelva a unirse a la reunión.

## Vea también

#### Conceptos

[Configuración de la página de participación en reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Plataformas admitidas en Lync Web App en Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)

