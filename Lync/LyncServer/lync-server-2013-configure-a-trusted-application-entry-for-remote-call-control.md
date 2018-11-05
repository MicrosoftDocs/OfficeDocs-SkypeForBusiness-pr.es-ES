---
title: "Configurar una entrada de aplicación de confianza para control remoto de llamadas"
TOCTitle: Configurar una entrada de aplicación de confianza para control remoto de llamadas
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48274947
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2015-11-02_

La puerta de enlace de SIP/CSTA debe configurarse como aplicación de confianza para que Lync Server aplique una ruta estática para enrutar llamadas a la puerta de enlace.

> [!IMPORTANT]  
> Si migra usuarios desde una implementación de una versión anterior de Lync Server, asegúrese de quitar todas las entradas de aplicación de confianza existentes (anteriormente conocidas como entradas de host autorizado) creadas para la puerta de enlace SIP/CSTA antes de seguir los procedimientos indicados en este tema. Para obtener más información, consulte <a href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Quitar un host autorizado heredado en Lync Server 2013 (opcional)</a>.



## Para configurar una entrada de aplicación de confianza para la puerta de enlace SIP/CSTA

1.  Inicie sesión en el equipo en el que está instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o un rol de control de acceso basado en roles (RBAC) al que haya asignado el cmdlet **New-CsTrustedApplicationPool**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para crear una entrada de aplicación de confianza, realice una de las siguientes acciones:
    
      - Para una conexión de Seguridad de la capa de transporte (TLS), escriba el siguiente comando en el símbolo del sistema:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Por ejemplo:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Para una conexión de Protocolo de control de transmisión (TCP), escriba el siguiente comando en el símbolo del sistema:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Por ejemplo:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Para agregar la aplicación de confianza al grupo, realice una de las siguientes acciones:
    
      - Para una conexión TLS, escriba el siguiente comando en el símbolo del sistema:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Por ejemplo:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Para una conexión TCP, escriba el siguiente comando en el símbolo del sistema:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Por ejemplo:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Para implementar los cambios publicados que haya efectuado a la topología, escriba el siguiente comando en el símbolo del sistema:
    
        Enable-CsTopology

## Vea también

#### Tareas

[Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

