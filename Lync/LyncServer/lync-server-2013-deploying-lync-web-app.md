---
title: 'Lync Server 2013: implementación de Lync Web App'
description: 'Lync Server 2013: implementación de Lync Web App.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce6fef02781afbd5bc5f315ce24bfb3bdb16df1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560426"
---
# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Implementación de Lync Web App en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-18_

Lync Web App es un cliente web de Internet Information Services (IIS) que se instala con Lync Server 2013 y está habilitado de forma predeterminada. No es necesario realizar ningún paso adicional para habilitar Lync Web App en el servidor o para implementar el cliente web en los usuarios. Cada vez que un usuario hace clic en una dirección URL de una reunión pero no tiene instalado el cliente de Lync 2013, se le presenta la opción de unirse a la reunión con la versión más reciente de Lync Web App.

Las características de voz, vídeo y uso compartido de Lync Web App requieren un control ActiveX de Microsoft. Puede instalar el control ActiveX con antelación o permitir a los usuarios que lo instalen cuando se le solicite, lo que ocurre la primera vez que usan Lync Web App o la primera vez que tienen acceso a una característica que requiere el control ActiveX.

<div class=" ">


> [!NOTE]  
> En las implementaciones del servidor perimetral 2013 de Lync Server, se requiere un proxy inverso HTTPS en la red perimetral para el acceso de cliente de Lync Web App. También debe publicar direcciones URL sencillas. Para obtener más información, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync server 2013</A> y <A href="lync-server-2013-planning-for-simple-urls.md">planeación de direcciones URL sencillas en Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Habilitación de multi-factor Authentication para Lync Web App

La versión de Lync Server 2013 de Lync Web App admite la autenticación de varios factores. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios que se unen desde redes externas cuando inician sesión en reuniones de Lync. Puede habilitar la autenticación multifactor mediante la implementación del servidor de Federación del servicio de Federación de Active Directory (AD FS) y la habilitación de la autenticación pasiva en Lync Server 2013. Una vez configurado AD FS, los usuarios externos que intenten unirse a reuniones de Lync reciben una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña junto con los métodos de autenticación adicionales que haya configurado.

<div class=" ">


> [!IMPORTANT]  
> A continuación, se indican algunas consideraciones importantes que debe tener en cuenta si tiene previsto configurar AD FS para la autenticación multifactor: 
> <UL>
> <LI>
> <P>La autenticación multifactor de ADFS funciona si el participante de la reunión y el organizador están en la misma organización o son de una organización federada de AD FS. La autenticación multifactor de ADFS no funciona para los usuarios federados de Lync porque la infraestructura Web de Lync Server no lo admite en este momento.</P>
> <LI>
> <P>Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes del cliente de Lync Web App se controlen con el mismo servidor front-end.</P>
> <LI>
> <P>Cuando establezca una relación de confianza para usuario autenticado entre los servidores de Lync Server y AD FS, asigne una duración de tokens lo suficientemente larga como para extender la longitud máxima de las reuniones de Lync. Normalmente, una duración de token de 240 minutos es suficiente.</P>
> <LI>
> <P>Esta configuración no se aplica a los clientes móviles de Lync.</P></LI></UL>



</div>

**Para configurar la autenticación multifactor**

1.  Instale un rol de servidor de Federación de AD FS. Para obtener más información, consulte la guía de implementación de los servicios de Federación de Active Directory 2,0 en <https://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Crear certificados para AD FS. Para obtener más información, consulte la sección "certificados de servidor de Federación" del tema Plan for and Deploy AD FS for use with Single Sign-on [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .

3.  Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Establezca una asociación mediante la ejecución del siguiente comando:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Establezca las siguientes reglas de usuario de confianza:
    
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

La característica BranchCache en Windows 7 y Windows Server 2008 R2 puede interferir con los componentes Web de Lync Web App. Para evitar problemas con los usuarios de Lync Web App, asegúrese de que BranchCache no esté habilitado.

Para obtener más información acerca de cómo deshabilitar BranchCache, consulte la guía de implementación de BranchCache, que está disponible en formato de Word en el centro de descarga de Microsoft, en [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) formato HTML en la biblioteca técnica de Windows Server 2008 R2, en [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) .

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Comprobación de la implementación de Lync Web App

Puede usar el cmdlet Test-CsUcwaConference para comprobar que un par de usuarios de prueba pueden participar en una conferencia mediante la API Web de comunicaciones unificadas (UCWA). Para obtener más información sobre este cmdlet, vea [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) en la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Solución de problemas de instalación de complementos en Windows Server 2008 R2

Si se produce un error en la instalación del complemento en un equipo que ejecuta Windows Server 2008 R2, es posible que deba modificar la configuración de seguridad de Internet Explorer o la configuración de la clave del registro DisableMSI.

**Para modificar la configuración de seguridad en Internet Explorer**

1.  Abra Internet Explorer.

2.  Haga clic en **herramientas**, en **Opciones de Internet**y, a continuación, en **avanzadas**.

3.  Desplácese hacia abajo hasta la sección **seguridad** .

4.  Desactive no **guardar las páginas cifradas en el disco**y, a continuación, haga clic en **Aceptar**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Si esta opción está activada, también se producirá un error al intentar descargar datos adjuntos de Lync Web App.

    
    </div>

5.  Vuelva a unirse a la reunión. El complemento debe descargarse sin errores.

**Para modificar la configuración del registro DisableMSI**

1.  Haga clic en **Inicio** y luego en **Ejecutar**.

2.  Para obtener acceso al editor del registro, escriba **regedit**.

3.  Vaya a HKEY \_ local \_ Machine \\ software \\ Policies \\ Microsoft \\ Windows \\ Installer.

4.  Edite o agregue la clave del registro DisableMSI de tipo REG \_ DWORD y establézcalo en 0.

5.  Vuelva a unirse a la reunión.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configuración de la página de participación en la reunión en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Plataformas compatibles con Lync Web App para Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

