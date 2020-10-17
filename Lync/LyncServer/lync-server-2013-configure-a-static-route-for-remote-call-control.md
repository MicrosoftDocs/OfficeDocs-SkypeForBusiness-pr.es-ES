---
title: 'Lync Server 2013: configurar una ruta estática para el control remoto de llamadas'
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
ms.openlocfilehash: d773658b17d846409e303c23204f86ea1f0fce77
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507677"
---
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

El control remoto de llamadas requiere que cada grupo de Lync Server esté configurado con una ruta de acceso desde ese grupo a la puerta de enlace SIP/CSTA que se conecta a la central de conmutación (PBX). Esta ruta necesita que cada grupo de servidores tenga una ruta estática para cada puerta de enlace a la que el grupo de servidores delegará mensajes de control de llamadas SIP asociados con llamadas a la central de conmutación. Si configura una ruta estática global para el control remoto de llamadas, cada grupo de servidores no configurado con una ruta estática en el nivel del grupo empleará la ruta estática global.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Para configurar una ruta estática para control remoto de llamadas

1.  Inicie sesión en un equipo en el que esté instalado shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o en un rol de control de acceso basado en roles (RBAC) al que haya asignado el cmdlet **New-CsStaticRoute** .

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Para crear una ruta estática y ponerla en la variable $TLSRoute o $TCPRoute, efectúe una de las acciones siguientes:
    
    <div class="">
    

    > [!TIP]  
    > Para establecer una coincidencia con los dominios secundarios de un dominio, use un valor de comodín en el parámetro MatchUri. Por ejemplo, <STRONG>*.contoso.net</STRONG>. Ese valor coincide con todos los dominios que tienen el sufijo <STRONG>contoso.net</STRONG>.

    
    </div>
    
      - Para una conexión de Seguridad de la capa de transporte (TLS), escriba el siguiente comando en el símbolo del sistema:
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Por ejemplo:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Si UseDefaultCertificate se define en False, debe especificar los parámetros TLSCertIssuer y TLSCertSerialNumber. Dichos parámetros indican, respectivamente, el nombre de la entidad de certificación que ha emitido el certificado empleado en la ruta estática y el número de serie de este certificado TLS. Para obtener más información acerca de estos parámetros, consulte Lync Server Management Shell Help escribiendo lo siguiente en el símbolo del sistema:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Para una conexión de Protocolo de control de transmisión (TCP), escriba el siguiente comando en el símbolo del sistema:
        
        <div class="">
        

        > [!NOTE]  
        > Si se especifica un nombre de dominio completo, primero debe configurar un registro A del Sistema de nombres de dominio (DNS).

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Por ejemplo:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        Después se muestran los valores predeterminados de los parámetros opcionales de rutas estáticas:
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        Recomendamos encarecidamente no cambiar estos valores predeterminados. Sin embargo, si debe cambiar cualquiera de estos parámetros, vea la ayuda del shell de administración de Lync Server escribiendo lo siguiente en el símbolo del sistema:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Para conservar una ruta estática recién creada en el almacén de administración central, ejecute una de las opciones siguientes, según corresponda:
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

