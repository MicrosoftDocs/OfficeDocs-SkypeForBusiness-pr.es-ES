---
title: Configuración de la autenticación pasiva de Lync Server
TOCTitle: Configuración de la autenticación pasiva de Lync Server
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn308569(v=OCS.15)
ms:contentKeyID: 56271325
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la autenticación pasiva de Lync Server

 

_**Última modificación del tema:** 2013-07-11_

En la siguiente sección, se describe cómo configurar Lync Server 2013 con Actualizaciones acumulativas: julio de 2013 para admitir la autenticación pasiva. Una vez habilitada, los usuarios que tengan habilitada la autenticación en dos fases tendrán que usar una tarjeta inteligente física o virtual y un PIN válido para iniciar sesión usando el cliente Lync 2013 con Actualizaciones acumulativas: julio de 2013.


> [!NOTE]
> Se recomienda encarecidamente a los clientes que habiliten la autenticación pasiva del registrador y los servicios web en el nivel de servicios. Si se habilita la autenticación pasiva del registrador y los servicios web en el nivel global, lo más probable es que se produzcan errores de autenticación en toda la organización cuando los usuarios no inicien sesión con el cliente de escritorio del cliente Lync 2013 con Actualizaciones acumulativas: julio de 2013.



## Configuración de servicios web

En los siguientes pasos, se describe cómo crear una configuración de servicios web personalizada para los Directores, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.

**Para crear una configuración de servicios web personalizada**

1.  Inicie sesión en su servidor front-end de Lync Server 2013 con Actualizaciones acumulativas: julio de 2013 usando una cuenta de administrador de Lync.

2.  Inicie el Shell de administración de Lync Server 2013.

3.  Desde la línea de comandos del Shell de administración de Lync Server, cree una nueva configuración de servicios web para cada Director, grupo de servidores Enterprise y servidor Standard Edition que estará habilitado para la autenticación pasiva. Para crearla, ejecute este comando:
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    
    > [!WARNING]  
    > El valor del FQDN WsFedPassiveMetadataUri FQDN es el Nombre del servicio de federación de su servidor AD FS 2.0. El valor de Nombre del servicio de federación se puede consultar en la consola de administración de AD FS 2.0 al hacer clic en <strong>Servicio</strong> en el panel de navegación y, luego, elegir <strong>Editar propiedades del servicio de federación</strong>.
    


4.  Para comprobar que los valores de UseWsFedPassiveAuth y WsFedPassiveMetadataUri se configuraron correctamente, ejecute el siguiente comando:
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  En los clientes, la autenticación pasiva es el método de autenticación menos preferido para la autenticación de WebTicket. En todos los Directores, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva, se deben deshabilitar todos los demás tipos de autenticación en los servicios web de Lync ejecutando el siguiente comando:
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación, ejecute el siguiente comando:
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

## Configuración de proxy

Cuando la autenticación de certificado esté deshabilitada para los servicios web de Lync, el cliente Lync usará un tipo de autenticación menos preferido, como Kerberos o NTLM, para autenticarse en el servicio registrador. La autenticación de certificado se sigue necesitando para permitir al cliente Lync que recupere un WebTicket, pero Kerberos y NTLM deben estar deshabilitados en el servicio registrador.

En los siguientes pasos, se describe cómo crear una configuración de proxy personalizada para los grupos de servidores perimetrales, grupos de servidores Enterprise y servidores Standard Edition que estarán habilitados para la autenticación pasiva.

**Para crear una configuración de proxy personalizada**

1.  Desde la línea de comandos del Shell de administración de Lync Server, cree una nueva configuración de proxy para cada grupo de servidores perimetrales, grupo de servidores Enterprise y servidor Standard Edition de Lync Server 2013 que estará habilitado para la autenticación pasiva. Para crearla, ejecute los siguientes comandos:
    
    ```
    New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
    -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
    ```
    ```
    New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
    -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
    ```

2.  Para comprobar que se han deshabilitado correctamente todos los demás tipos de autenticación de proxy, ejecute el siguiente comando:
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth

