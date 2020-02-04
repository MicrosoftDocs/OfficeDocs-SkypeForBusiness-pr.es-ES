---
title: 'Lync Server 2013: Configurar una ruta estática para el control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfb825e51a9beec7010f9f46ed0fc649267897fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

El control remoto de llamadas requiere que cada grupo de servidores Lync esté configurado con una ruta de acceso de ese grupo a la puerta de enlace SIP/CSTA que se conecta a la central de conmutación (PBX). Esta ruta requiere que cada grupo tenga una ruta estática para cada una de las puertas de enlace a las que el grupo se dirigirá por proxy los mensajes de control de llamada SIP asociados con llamadas a la PBX. Si configura una ruta estática global para el control remoto de llamadas, cada grupo de servidores que no esté configurado con una ruta estática en el nivel del grupo usará la ruta estática global.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Para configurar una ruta estática para el control remoto de llamadas

1.  Inicie sesión en un equipo en el que esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o en un rol de control de acceso basado en roles (RBAC) al que haya asignado el cmdlet **New-CsStaticRoute** .

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Para crear una ruta estática y colocarla en la variable $TLSRoute o $TCPRoute, realice una de las siguientes acciones:
    
    <div class="">
    

    > [!TIP]  
    > Para que coincidan los dominios secundarios de un dominio, puede especificar un valor comodín en el parámetro MatchUri. Por ejemplo, <STRONG>*. contoso.net</STRONG>. Ese valor coincide con cualquier dominio que termine con el sufijo <STRONG>contoso.net</STRONG>.

    
    </div>
    
      - Para una conexión de seguridad de nivel de transporte (TLS), escriba lo siguiente en el símbolo del sistema:
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Por ejemplo:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Si UseDefaultCertificate se establece en false, debe especificar parámetros TLSCertIssuer y TLSCertSerialNumber. Estos parámetros indican el nombre de la entidad de certificación (CA) que emitió el certificado que se usó en la ruta estática y el número de serie de ese certificado TLS, respectivamente. Para obtener más información sobre estos parámetros, consulte la ayuda del shell de administración de Lync Server escribiendo lo siguiente en el símbolo del sistema:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Para una conexión de protocolo de control de transmisión (TCP), escriba lo siguiente en el símbolo del sistema:
        
        <div class="">
        

        > [!NOTE]  
        > Si especifica un nombre de dominio completo (FQDN), primero debe configurar un registro DNS (sistema de nombres de dominio).

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Por ejemplo:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        A continuación se muestran los valores predeterminados de parámetros opcionales para rutas estáticas:
        
          - Enabled = true
        
          - MatchOnlyPhoneUri = false
        
          - ReplaceHostInRequestUri = false
        
        Le recomendamos encarecidamente que no cambie estos valores predeterminados. Sin embargo, si tiene que cambiar alguno de estos parámetros, consulte la ayuda del shell de administración de Lync Server escribiendo lo siguiente en el símbolo del sistema:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Para conservar una ruta estática recién creada en el almacén de administración central, ejecute una de las siguientes opciones, según corresponda:
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

