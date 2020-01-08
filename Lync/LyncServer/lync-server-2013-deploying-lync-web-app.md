---
title: 'Lync Server 2013: implementación de Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c355be1c1709cede9c032d59790d6beefb337ff6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Implementar Lync Web App en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-18_

Lync Web App es un cliente web de Internet Information Services (IIS) que se instala con Lync Server 2013 y está habilitado de forma predeterminada. No se necesitan pasos adicionales para habilitar Lync Web App en el servidor o para implementar el cliente web a los usuarios. Siempre que un usuario haga clic en una dirección URL de la reunión pero no tenga instalado el cliente 2013 de Lync, se le presentará al usuario la opción de unirse a la reunión con la versión más reciente de Lync Web App.

Las características de voz, vídeo y uso compartido de Lync Web App requieren un control ActiveX de Microsoft. Puede instalar el control ActiveX por adelantado o permitir que los usuarios lo instalen cuando se le pida, lo que sucede la primera vez que usa Lync Web App o la primera vez que accede a una característica que requiere el control ActiveX.

<div class=" ">


> [!NOTE]  
> En las implementaciones de servidor perimetral de Lync Server 2013, se requiere un proxy inverso HTTPS en la red perimetral para el acceso de cliente de Lync Web App. También debe publicar direcciones URL sencillas. Para obtener más información, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync server 2013</A> y <A href="lync-server-2013-planning-for-simple-urls.md">planeamiento de direcciones URL simples en Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Habilitar la autenticación multifactor para Lync Web App

La versión de Lync Server 2013 de Lync Web App admite la autenticación multifactor. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar usuarios que se unan desde redes externas cuando inicien sesión en reuniones de Lync. Puede habilitar la autenticación multifactor si implementa el servidor de Federación de servicio de Federación de Active Directory (AD FS) y habilita la autenticación pasiva en Lync Server 2013. Después de configurar AD FS, los usuarios externos que intenten unirse a reuniones de Lync se presentan con una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña, junto con los métodos de autenticación adicionales que haya configurado. .

<div class=" ">


> [!IMPORTANT]  
> A continuación, se incluyen algunas consideraciones importantes para planear la configuración de AD FS para la autenticación multifactor: 
> <UL>
> <LI>
> <P>La autenticación multifactor de AD FS funciona si el usuario que participa en la reunión y el organizador están en la misma organización o si ambos provienen de una organización federada de AD FS. La autenticación multifactor de AD FS no funciona para usuarios federados de Lync porque la infraestructura web de Lync Server no lo admite en este momento.</P>
> <LI>
> <P>Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes del cliente de Lync Web App se controlen mediante el mismo servidor front-end.</P>
> <LI>
> <P>Al establecer una relación de confianza para usuario autenticado entre Lync Server y los servidores AD FS, asigne un símbolo de vida que sea lo suficientemente largo para que se extienda la longitud máxima de las reuniones de Lync. Por lo general, una duración de token de 240 minutos es suficiente.</P>
> <LI>
> <P>Esta configuración no se aplica a los clientes móviles de Lync.</P></LI></UL>



</div>

**Para configurar la autenticación multifactor**

1.  Instale un rol del servidor de federación de AD FS. Para obtener más información, consulte la guía de implementación de servicios de Federación de Active Directory 2,0 en<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Cree certificados para AD FS. Para obtener más información, consulte la sección "certificados de servidor de Federación" de los temas planear e implementar AD FS para su uso con el inicio [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)de sesión único en.

3.  Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Establezca una relación de usuario mediante la ejecución del siguiente comando:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Defina las siguientes reglas de usuario de confianza:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>Configuración de BranchCache

La característica BranchCache en Windows 7 y Windows Server 2008 R2 puede interferir con los componentes Web de Lync Web App. Para evitar problemas con los usuarios de Lync Web App, asegúrese de que BranchCache no está habilitado.

Para más información sobre cómo deshabilitar BranchCache, consulte la guía de implementación de BranchCache, que está disponible en formato de Word en [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) el centro de descarga de Microsoft, en formato HTML, en la [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)biblioteca técnica de Windows Server 2008 R2 en.

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Comprobar la implementación de Lync Web App

Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba puedan participar de una conferencia con la API web de comunicaciones unificadas (UCWA). Para obtener más información sobre este cmdlet, vea [probar-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) en la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Solución de problemas de instalación de complementos en Windows Server 2008 R2

Si se produce un error en la instalación del complemento en un equipo con Windows Server 2008 R2, es posible que tenga que modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del registro DisableMSI.

**Para modificar la configuración de seguridad en Internet Explorer**

1.  Abra Internet Explorer.

2.  Haga clic en **Herramientas **, en **Opciones de Internet** y en **Opciones avanzadas**.

3.  Desplácese hacia abajo hasta la sección **Seguridad**.

4.  Desactive **No guardar las páginas cifradas en el disco** y haga clic en **Aceptar**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Si se selecciona, esta configuración también provocará un error al intentar descargar datos adjuntos desde Lync Web App.

    
    </div>

5.  Vuelva a unirse a la reunión. El complemento se debe descargar sin errores.

**Para modificar la configuración del registro DisableMSI**

1.  Haga clic en  **Inicio ** y en  **Ejecutar **.

2.  Para acceder al Editor del Registro, escriba **regedit**.

3.  Vaya a HKEY\_local\_Machine\\software\\\\Policies\\Microsoft\\Windows Installer.

4.  Edite o agregue la clave del registro DisableMSI de\_escriba REG DWORD y establézcalo en 0.

5.  Vuelva a unirse a la reunión.

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la página de participación en reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Plataformas compatibles con Lync Web App para Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

