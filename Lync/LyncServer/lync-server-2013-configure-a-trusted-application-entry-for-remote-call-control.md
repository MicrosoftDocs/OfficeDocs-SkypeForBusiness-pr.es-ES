---
title: Configurar una entrada de aplicación de confianza para control remoto de llamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0dda3eedc73e5c64f7c275714955f3ce92af3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-11-02_

La puerta de enlace SIP/CSTA debe estar configurada como aplicación de confianza para que Lync Server pueda aplicar una ruta estática para enrutar llamadas a la puerta de enlace.

<div>


> [!IMPORTANT]
> Si va a migrar usuarios de una versión anterior de la implementación de Lync Server, asegúrese de que ha quitado todas las entradas de aplicaciones de confianza existentes (anteriormente conocidas como entradas de host autorizadas) que ha creado para la puerta de enlace SIP/CSTA antes de seguir los procedimientos de este tema. Para obtener más información, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">quitar un host autorizado heredado en Lync Server 2013 (opcional)</A>.<BR>Si tiene previsto implementar un control de llamada remota nuevo mediante una conexión de protocolo de control de transmisión (TCP), debe comprobar que el <STRONG>uso del servicio para las direcciones IP seleccionadas</STRONG> debe establecerse en las aplicaciones y grupos de confianza existentes, si quiere usar el mismo Puerto TCP para la nueva aplicación de confianza.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>Para configurar una entrada de aplicación de confianza para la puerta de enlace SIP/CSTA

1.  Inicie sesión en el equipo en el que está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o en un rol de control de acceso basado en roles (RBAC) al que haya asignado el cmdlet **New-CsTrustedApplicationPool** .

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Para crear una entrada de aplicación de confianza, realice una de las siguientes acciones:
    
      - Para una conexión de seguridad de nivel de transporte (TLS), escriba lo siguiente en el símbolo del sistema:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Por ejemplo:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Para una conexión de protocolo de control de transmisión (TCP), escriba lo siguiente en el símbolo del sistema:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Por ejemplo:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Para agregar la aplicación de confianza al grupo, realice una de las siguientes acciones:
    
      - Para una conexión TLS, escriba lo siguiente en el símbolo del sistema:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Por ejemplo:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Para una conexión TCP, escriba lo siguiente en el símbolo del sistema:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Por ejemplo:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Para implementar los cambios publicados que ha realizado en la topología, escriba lo siguiente en el símbolo del sistema:
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

