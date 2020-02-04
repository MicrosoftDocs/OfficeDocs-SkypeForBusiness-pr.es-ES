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
ms.openlocfilehash: 0a2e52f957a8aba7e69e97b0ec2100ffbc5a190c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Configuración de la autenticación pasiva de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-11_

En la sección siguiente se describe cómo configurar Lync Server 2013 con las actualizaciones acumulativas: 2013 de julio para admitir la autenticación pasiva. Una vez habilitado, los usuarios de Lync que tengan habilitada la autenticación de dos factores deberán usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión con la 2013 de Lync con las actualizaciones acumulativas: cliente de 2013 de julio.

<div class="">


> [!NOTE]  
> Se recomienda encarecidamente a los clientes que habiliten la autenticación pasiva del registrador y los servicios web en el nivel de servicios. Si la autenticación pasiva está habilitada para el registrador y los servicios web en el nivel global, es probable que se produzcan errores de autenticación en toda la organización para los usuarios que no están iniciando sesión con el 2013 de Lync con las actualizaciones acumulativas: cliente de escritorio cliente de 2013 de julio.



</div>

<div>

## <a name="web-service-configuration"></a>Configuración de servicios web

En los siguientes pasos, se describe cómo crear una configuración de servicios web personalizada para los Directores, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.

**Para crear una configuración de servicios web personalizada**

1.  Inicie sesión en su Lync Server 2013 con las actualizaciones acumulativas: 2013 servidor front-end de julio mediante una cuenta de administrador de Lync.

2.  Inicie el shell de administración de Lync Server 2013.

3.  Desde la línea de comandos del shell de administración de Lync Server, cree una nueva configuración de servicio web para cada director, grupo de servidores Enterprise y servidor Standard Edition que se habilitará para la autenticación pasiva ejecutando el siguiente comando:
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > El valor del FQDN WsFedPassiveMetadataUri es el Nombre del servicio de federación de su servidor AD FS 2.0. El valor de Nombre del servicio de federación se puede consultar en la consola de administración de AD FS 2.0 al hacer clic en <STRONG>Servicio</STRONG> en el panel de navegación y, luego, elegir <STRONG>Editar propiedades del servicio de federación</STRONG>.

    
    </div>

4.  Para comprobar que los valores de UseWsFedPassiveAuth y WsFedPassiveMetadataUri se configuraron correctamente, ejecute el siguiente comando:
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  En los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de WebTicket. Para todos los directores, grupos empresariales y servidores Standard Edition que se habilitarán para la autenticación pasiva, todos los demás tipos de autenticación deben estar deshabilitados en los servicios Web de Lync ejecutando el siguiente comando:
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Compruebe que todos los demás tipos de autenticación se han deshabilitado ejecutando el siguiente comando:
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Configuración de proxy

Cuando la autenticación de certificados está deshabilitada para los servicios Web de Lync, el cliente de Lync usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticar el servicio de registro. La autenticación de certificados sigue siendo necesaria para permitir que el cliente de Lync recupere un webvale, pero Kerberos y NTLM deben estar deshabilitados para el servicio de registro.

En los siguientes pasos, se describe cómo crear una configuración de proxy personalizada para los grupos de servidores perimetrales, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.

**Para crear una configuración de proxy personalizada**

1.  Desde la línea de comandos del shell de administración de Lync Server, cree una nueva configuración de proxy para cada servidor de Lync 2013 con actualizaciones acumulativas: 2013 de julio, grupo de servidores Enterprise y servidor Standard Edition que se habilitarán para la autenticación pasiva mediante la ejecución de la siguientes comandos:
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación de proxy, ejecute el siguiente comando:
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

