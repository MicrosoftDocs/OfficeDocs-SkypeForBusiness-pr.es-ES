---
title: 'Lync Server 2013: implementación de la aplicación de la tienda Windows de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b22880b230acda74c7485010550d5576ea200c61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Implementación de la aplicación de la tienda Windows de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-03_

Antes de hacer que la aplicación de la tienda Windows de Lync esté disponible para los usuarios, asegúrese de que la implementación cumple los [requisitos de la aplicación de la tienda Windows de Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Para obtener más información sobre cómo configurar Lync Server 2013 para admitir la aplicación de la tienda Windows de Lync, consulte el artículo del blog de NextHop, "detección automática de Lync [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Server y la aplicación de la tienda Windows de Lync", en. Una vez que el entorno de servidor esté configurado correctamente, puede dirigir a los usuarios para que descarguen la aplicación de Lync desde la tienda Windows buscando "Lync".

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Habilitar la autenticación multifactor para la aplicación de la tienda Windows de Lync

Actualizaciones acumulativas para Lync Server 2013: el 2013 de junio agrega compatibilidad con la autenticación multifactor para los clientes de la aplicación de la tienda Windows de Lync. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar usuarios externos cuando inician sesión en reuniones de Lync. Para habilitar la autenticación multifactor, debe implementar el servidor de Federación de servicio de Federación de Active Directory (AD FS) y habilitar la autenticación pasiva en Lync Server 2013. Después de configurar AD FS, los usuarios externos que intenten unirse a reuniones de Lync se presentan con una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña, junto con los métodos de autenticación adicionales que haya configurado. .

<div class=" ">


> [!IMPORTANT]  
> A continuación se indican algunas consideraciones importantes si tiene previsto configurar AD FS para la autenticación multifactor para la aplicación de la tienda Windows de Lync: 
> <UL>
> <LI>
> <P>Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: se necesita, como mínimo, el 2013 de junio. Los clientes de escritorio de Lync 2013 no requieren actualizaciones acumulativas para Lync Server 2013:2013 de junio, por lo que podría parecer que la autenticación pasiva funciona correctamente porque los clientes de Lync 2013 pueden autenticarse. Sin embargo, el proceso de autenticación para los clientes de la aplicación de la tienda Windows Lync no se completará y no se mostrará ninguna notificación o mensaje de error.</P>
> <LI>
> <P>El servidor debe estar configurado de modo que la autenticación pasiva sea el único tipo de autenticación ofrecido.</P>
> <LI>
> <P>Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes del cliente de la aplicación de la tienda Windows de Lync se controlen mediante el mismo servidor front-end.</P>
> <LI>
> <P>Al establecer una relación de confianza para usuario autenticado entre Lync Server y los servidores AD FS, asigne un símbolo de vida que sea lo suficientemente largo para que se extienda la longitud máxima de las reuniones de Lync. Por lo general, una duración de token de 240 minutos es suficiente.</P></LI></UL>



</div>

**Para configurar la autenticación multifactor**

1.  Instale un rol del servidor de federación de AD FS. Para obtener más información, consulte la guía de implementación de servicios de <http://go.microsoft.com/fwlink/p/?linkid=267511>Federación de active directory 2,0 en.

2.  Cree certificados para AD FS. Para obtener más información, consulte la sección "certificados de servidor de Federación" de los temas planear e implementar AD FS para su uso con el inicio [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)de sesión único en.

3.  Desde la interfaz de línea de comandos de Windows PowerShell, ejecute el siguiente comando:
    
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

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Problemas conocidos que pueden impedir el inicio de sesión

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>La fecha y la hora no se establecen correctamente en el dispositivo que ejecuta la aplicación de la tienda Windows de Lync

La configuración de hora del dispositivo debe estar sincronizada con la configuración de hora del servidor. Esto es especialmente importante para dispositivos como Microsoft Surface y otros dispositivos que ejecutan Windows RT que no están Unidos a un dominio. Para establecer la hora en estos dispositivos de forma automática desde un servidor de hora, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados en el dispositivo:

    w32tm /resync

</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Aplicación de la tienda Windows de Lync no se puede acceder al servidor o servicios de Lync

Es posible que la aplicación Lync Windows Store no pueda acceder al servidor o los servicios de Lync a través de adaptadores de red, como los módems 4G LTE USB, que no se registran en Windows 8 como dispositivos físicos. Es posible que la aplicación de la tienda Windows de Lync tenga este problema incluso cuando las aplicaciones de escritorio y los exploradores puedan acceder a otros servidores y sitios Web.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Aplicación de la tienda Windows de Lync no se puede iniciar sesión con Lync Server 2010 y el servidor perimetral de Office Communications Server 2007 R2

Si su topología consta de Lync Server 2010 con el servidor perimetral R2 de Office Communications Server 2007, tendrá que ejecutar la versión actualizada de Topology Builder disponible en la actualización acumulativa para Lync Server 2010: de 2013 julio. Las versiones anteriores de Topology Builder no crean la asignación requerida para Office Communications Server 2007 Edge Server, por lo que los clientes de la aplicación de la tienda Windows Lync no pueden iniciar sesión. Los pasos siguientes son necesarios:

1.  Instale la actualización acumulativa para Lync Server 2010:2013 de julio en los grupos de Lync Server 2010 y los directores de Lync Server 2010.

2.  Actualice la configuración de detección automática de Lync para indicar que el punto de entrada SIP externo es la dirección del servidor perimetral haciendo lo siguiente:
    
    1.  Abra el Shell de administración de Lync Server.
    
    2.  Ejecute el siguiente comando:
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>La aplicación de la tienda Windows de Lync no puede iniciar sesión debido a un error de validación de nombre de certificado

Puede producirse un problema de inicio de sesión para los usuarios de Office 365 que no ejecutan la versión más reciente de la aplicación de la tienda Windows de Lync. Este problema suele ocurrir cuando se usan varios dominios (por ejemplo, cuando el URI del SIP es **Usera@domainZ.com** pero el servidor perimetral es **SIP.domainX.com**). Para solucionar el problema, los usuarios deben instalar la última versión de la aplicación Lync de la tienda Windows, que también requiere Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Usar los registros de la aplicación Lync Windows Store para solucionar problemas

Puede usar los registros generados en el dispositivo para solucionar problemas. Los registros se almacenan en la siguiente carpeta:

% LocalAppData%\\Packages\\Microsoft.\_LyncMX\\8wekyb3d8bbwe\\LocalState Tracing

Antes de obtener los registros de un usuario, asegúrese de que el registro esté activado y, a continuación, pida al usuario que guarde los registros para que toda la información almacenada en la memoria también se guarde en los archivos del disco duro.

**Para activar el registro**

1.  Abra la aplicación de la tienda Windows de Lync en el dispositivo.

2.  Deslice el dedo desde el lado derecho de la pantalla. Si usa un mouse, apunte a la esquina superior derecha de la pantalla y, a continuación, mueva el puntero del mouse hacia abajo en la pantalla.

3.  Seleccione **configuración**, seleccione **Opciones**y, a continuación, establezca registros **de** **diagnóstico** en activado.

4.  Si los **registros de diagnóstico** estaban deshabilitados anteriormente, debe reiniciar Lync. Para reiniciar Lync, siga uno de estos procedimientos:
    
      - Reinicie el dispositivo.
    
      - Finalice la tarea de Lync y vuelva a iniciar la aplicación. Para finalizar la tarea, abra el administrador de tareas de Windows, seleccione **Lync**y, a continuación, puntee en **Finalizar tarea**. Si Lync no aparece en la lista, pulse **más detalles** y busque Lync en **procesos en segundo plano**.

**Para guardar los registros**

1.  Abra la aplicación de la tienda Windows de Lync en el dispositivo.

2.  Intente iniciar sesión.

3.  Deslice el dedo desde el lado derecho de la pantalla. Si usa un mouse, apunte a la esquina superior derecha de la pantalla y, a continuación, mueva el puntero del mouse hacia abajo en la pantalla.

4.  Seleccione **configuración**, seleccione **acerca**de y, a continuación, haga clic en **guardar registros**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

