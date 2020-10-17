---
title: 'Lync Server 2013: implementación de la aplicación de la tienda Windows de Lync'
description: 'Lync Server 2013: implementación de la aplicación Lync de la tienda Windows.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9260d656079fb694a14aadf5049ca36241830c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571716"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Implementación de la aplicación Lync de la tienda Windows en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-03_

Antes de poner a disposición de los usuarios la aplicación Lync de la tienda Windows, asegúrese de que la implementación cumple los [requisitos de la aplicación de Lync para Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Para obtener más información sobre cómo configurar Lync Server 2013 para que admita la aplicación Lync de la tienda Windows, vea el artículo del blog NextHop, "Lync Server Autodiscover y la aplicación Lync Windows Store", en [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) . Una vez configurado correctamente el entorno de servidor, puede dirigir a los usuarios para que descarguen la aplicación Lync desde la tienda Windows buscando "Lync".

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Habilitar la autenticación multifactor para la aplicación de la tienda Windows de Lync

Actualizaciones acumulativas para Lync Server 2013: el 2013 de junio agrega compatibilidad con la autenticación multifactor para los clientes de la aplicación de la tienda Windows de Lync. Además del nombre de usuario y la contraseña, puede requerir métodos de autenticación adicionales, como tarjetas inteligentes o PIN, para autenticar a los usuarios externos cuando inician sesión en reuniones de Lync. Para habilitar la autenticación multifactor, debe implementar el servidor de Federación del servicio de Federación de Active Directory (AD FS) y habilitar la autenticación pasiva en Lync Server 2013. Una vez configurado AD FS, los usuarios externos que intenten unirse a reuniones de Lync reciben una página web de autenticación multifactor de AD FS que contiene el desafío de nombre de usuario y contraseña junto con los métodos de autenticación adicionales que haya configurado.

<div class=" ">


> [!IMPORTANT]  
> Las siguientes son consideraciones importantes si planea configurar AD FS para la autenticación multifactor para la aplicación de la tienda Windows de Lync: 
> <UL>
> <LI>
> <P>Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: se requiere junio de 2013 como mínimo. Los clientes de escritorio de Lync 2013 no requieren actualizaciones acumulativas para Lync Server 2013: junio de 2013, por lo que puede parecer que la autenticación pasiva funciona porque los clientes de Lync 2013 pueden realizar la autenticación. Sin embargo, el proceso de autenticación para los clientes de la aplicación de la tienda Windows Lync no se completará y no se mostrará ningún mensaje de notificación o error.</P>
> <LI>
> <P>El servidor debe estar configurado para que la autenticación pasiva sea el único tipo de autenticación ofrecido.</P>
> <LI>
> <P>Si usa equilibradores de carga de hardware, habilite la persistencia de las cookies en los equilibradores de carga para que todas las solicitudes del cliente de la aplicación de la tienda Windows de Lync se controlen con el mismo servidor front-end.</P>
> <LI>
> <P>Cuando establezca una relación de confianza para usuario autenticado entre los servidores de Lync Server y AD FS, asigne una duración de tokens lo suficientemente larga como para extender la longitud máxima de las reuniones de Lync. Normalmente, una duración de token de 240 minutos es suficiente.</P></LI></UL>



</div>

**Para configurar la autenticación multifactor**

1.  Instale un rol de servidor de Federación de AD FS. Para obtener más información, consulte la guía de implementación de los servicios de Federación de Active Directory 2,0 en <https://go.microsoft.com/fwlink/p/?linkid=267511> .

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
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Problemas conocidos que pueden impedir el inicio de sesión

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>La hora y la fecha no se establecen correctamente en el dispositivo que ejecuta la aplicación Lync de la tienda Windows

La configuración de la hora en el dispositivo debe estar sincronizada con la configuración de hora en el servidor. Esto es especialmente importante para dispositivos como Microsoft Surface y otros dispositivos que ejecutan Windows RT que no están Unidos a un dominio. Para establecer la hora en estos dispositivos automáticamente desde un servidor de hora, ejecute el siguiente comando desde un símbolo del sistema con privilegios elevados en el dispositivo:
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync la aplicación de la tienda Windows no puede acceder a Lync Server o a los servicios

Es posible que la aplicación Lync de la tienda Windows no pueda obtener acceso a Lync Server o a los servicios a través de adaptadores de red, como los módems USB de 4G LTE, que no se registran en Windows 8 como dispositivos físicos. Lync la aplicación de la tienda Windows puede tener este problema incluso cuando las aplicaciones de escritorio y los exploradores puedan acceder a otros servidores y sitios Web.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Lync la aplicación de la tienda Windows no puede iniciar sesión con el servidor perimetral de Lync Server 2010 y Office Communications Server 2007 R2

Si su topología consta de Lync Server 2010 con Office Communications Server 2007 R2 Edge Server, tendrá que ejecutar la versión actualizada del generador de topologías disponible en la actualización acumulativa de Lync Server 2010: de julio de 2013. Las versiones anteriores del generador de topologías no crean la asignación necesaria al servidor perimetral de Office Communications Server 2007, por lo que los clientes de la aplicación de la tienda Windows de Lync no pueden iniciar sesión. Se requieren los pasos siguientes:

1.  Instale la actualización acumulativa para Lync Server 2010:2013 de julio en los grupos de servidores de Lync Server 2010 y los directores de Lync Server 2010.

2.  Actualice la configuración de detección automática de Lync para indicar que el punto de entrada SIP externo es la dirección del servidor perimetral; para ello, haga lo siguiente:
    
    1.  Abra el shell de administración de Lync Server.
    
    2.  Ejecute el siguiente comando:
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>Lync la aplicación de la tienda Windows no puede iniciar sesión debido a un error de validación de nombre de certificado

Puede producirse un problema de inicio de sesión para los usuarios de Microsoft 365 o Office 365 que no ejecutan la versión más reciente de la aplicación de la tienda Windows de Lync. Este problema suele producirse cuando se usan varios dominios (por ejemplo, cuando el URI del SIP es **Usera@domainZ.com** pero el servidor perimetral es **SIP.domainX.com**). Para solucionar el problema, los usuarios deben instalar la última versión de la aplicación Lync de la tienda Windows, que también requiere Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Usar registros de aplicación de la tienda Windows Lync para solucionar problemas

Puede usar los registros generados en el dispositivo para solucionar problemas. Los registros se almacenan en la carpeta siguiente:

% LocalAppData% \\ Packages \\ Microsoft. LyncMX \_ 8wekyb3d8bbwe \\ LocalState \\ Tracing

Antes de obtener los registros de un usuario, asegúrese de que esté activado el registro y, a continuación, pida al usuario que guarde los registros para que toda la información almacenada en la memoria también se guarde en los archivos del disco duro.

**Para activar el registro**

1.  Abra la aplicación Lync de la tienda Windows en el dispositivo.

2.  Deslice el dedo desde el lado derecho de la pantalla. Si está usando un mouse, coloque el puntero en la esquina superior derecha de la pantalla y, a continuación, mueva el puntero del mouse hacia abajo en la pantalla.

3.  Seleccione **configuración**, seleccione **Opciones**y, después, establezca los registros **de** **diagnóstico** en activado.

4.  Si los **registros de diagnóstico** se desactivaron anteriormente, debe reiniciar Lync. Para reiniciar Lync, siga uno de estos procedimientos:
    
      - Reinicie el dispositivo.
    
      - Finalice la tarea de Lync y vuelva a iniciar la aplicación. Para finalizar la tarea, abra el administrador de tareas de Windows, seleccione **Lync**y, a continuación, puntee en **Finalizar tarea**. Si Lync no aparece en la lista, pulse **más detalles** y busque Lync en **procesos en segundo plano**.

**Para guardar los registros**

1.  Abra la aplicación Lync de la tienda Windows en el dispositivo.

2.  Intente iniciar sesión.

3.  Deslice el dedo desde el lado derecho de la pantalla. Si está usando un mouse, coloque el puntero en la esquina superior derecha de la pantalla y, a continuación, mueva el puntero del mouse hacia abajo en la pantalla.

4.  Seleccione **configuración**, seleccione **acerca**de y, a continuación, seleccione **guardar registros**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

