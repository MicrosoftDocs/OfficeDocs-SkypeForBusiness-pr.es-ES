---
title: 'Lync Server 2013: configuración de la autenticación pasiva'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 780b539aeaf6a6bc6956fc5f8b6185092675632b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532497"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a>Configuración de la autenticación pasiva de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-11_

En la siguiente sección se describe cómo configurar Lync Server 2013 con actualizaciones acumulativas: 2013 julio para admitir la autenticación pasiva. Una vez habilitado, los usuarios de Lync que tengan habilitada la autenticación en dos fases deberán usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión mediante el cliente de Lync 2013 con actualizaciones acumulativas: cliente de 2013 de julio.

<div class="">


> [!NOTE]  
> Se recomienda encarecidamente que los clientes habiliten la autenticación pasiva para el registrador y los servicios web en el nivel de servicio. Si la autenticación pasiva está habilitada para el registrador y los servicios web en el nivel global, es probable que se produzcan errores de autenticación en toda la organización para los usuarios que no inician sesión con el cliente de escritorio de Lync 2013 con actualizaciones acumulativas: cliente de escritorio del cliente de julio de 2013.



</div>

<div>

## <a name="web-service-configuration"></a>Configuración del servicio Web

En los siguientes pasos se describe cómo crear una configuración de servicio web personalizada para directores, grupos de servidores Enterprise y servidores Standard Edition que se habilitarán para la autenticación pasiva.

**Para crear una configuración de servicio web personalizada**

1.  Inicie sesión en su Lync Server 2013 con actualizaciones acumulativas: 2013 servidor front-end de julio con una cuenta de administrador de Lync.

2.  Inicie el shell de administración de Lync Server 2013.

3.  Desde la línea de comandos del shell de administración de Lync Server, cree una nueva configuración de servicio web para cada director, grupo de servidores Enterprise y servidor Standard Edition que se habilitará para la autenticación pasiva mediante la ejecución del siguiente comando:
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > El valor para el FQDN WsFedPassiveMetadataUri es el nombre del servicio de Federación del servidor 2,0 de AD FS. El valor del nombre del servicio de Federación se puede encontrar en la consola de administración de AD FS 2,0 al hacer clic con el botón secundario en <STRONG>servicio</STRONG> en el panel de navegación y, a continuación, seleccionar <STRONG>Editar propiedades del servicio de Federación</STRONG>.

    
    </div>

4.  Ejecute el siguiente comando para comprobar que los valores para y WsFedPassiveMetadataUri se establecieron correctamente:
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Para los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de webticket. Para todos los directores, grupos de servidores Enterprise y servidores Standard Edition que se habilitarán para la autenticación pasiva, todos los demás tipos de autenticación deben estar deshabilitados en servicios Web de Lync ejecutando el siguiente comando:
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Ejecute el siguiente comando para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación:
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Configuración de proxy

Cuando la autenticación de certificados está deshabilitada para los servicios Web de Lync, el cliente de Lync usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticarse en el servicio de registrador. La autenticación de certificados sigue siendo necesaria para permitir que el cliente de Lync recupere un webvale, pero Kerberos y NTLM deben estar deshabilitados para el servicio de registrador.

En los pasos siguientes se describe cómo crear una configuración de proxy personalizada para los grupos de servidores perimetrales, grupos de servidores Enterprise y servidores Standard Edition que se habilitarán para la autenticación pasiva.

**Para crear una configuración de proxy personalizada**

1.  Desde la línea de comandos del shell de administración de Lync Server, cree una nueva configuración de proxy para cada Lync Server 2013 con actualizaciones acumulativas: 2013 de julio de grupo de servidores perimetrales, grupo de servidores Enterprise y servidor Standard Edition que se habilitarán para la autenticación pasiva mediante la ejecución de los siguientes comandos:
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Ejecute el siguiente comando para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación de proxy:
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

