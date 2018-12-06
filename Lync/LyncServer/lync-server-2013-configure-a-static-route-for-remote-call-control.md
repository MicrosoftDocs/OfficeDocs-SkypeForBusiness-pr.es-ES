---
title: "Lync Server 2013: Configurar ruta estática para el control remoto de llamadas"
TOCTitle: Configurar una ruta estática para el control remoto de llamadas
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48277194
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-22_

El control remoto de llamadas precisa que cada grupo de servidores de Lync Server se configure con una ruta que va de ese grupo de servidores a la puerta de enlace de SIP/CSTA que se conecta con la central de conmutación (PBX). Esta ruta necesita que cada grupo de servidores tenga una ruta estática para cada puerta de enlace a la que el grupo de servidores delegará mensajes de control de llamadas SIP asociados con llamadas a la central de conmutación. Si configura una ruta estática global para el control remoto de llamadas, cada grupo de servidores no configurado con una ruta estática en el nivel del grupo empleará la ruta estática global.

## Para configurar una ruta estática para control remoto de llamadas

1.  Inicie sesión en un equipo en el que Shell de administración de Lync Server esté instalado como miembro del grupo RTCUniversalServerAdmins o un rol de control de acceso basado en roles al que haya asignado el cmdlet **New-CsStaticRoute**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para crear una ruta estática y ponerla en la variable $TLSRoute o $TCPRoute, efectúe una de las acciones siguientes:
    
    > [!TIP]  
    > Para establecer una coincidencia con los dominios secundarios de un dominio, use un valor de comodín en el parámetro MatchUri. Por ejemplo, <strong>*.contoso.net</strong>. Ese valor coincide con todos los dominios que tienen el sufijo <strong>contoso.net</strong>.
    
    
      - Para una conexión de Seguridad de la capa de transporte (TLS), escriba el siguiente comando en el símbolo del sistema:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        Por ejemplo:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        Si UseDefaultCertificate se define en False, debe especificar los parámetros TLSCertIssuer y TLSCertSerialNumber. Dichos parámetros indican, respectivamente, el nombre de la entidad de certificación que ha emitido el certificado empleado en la ruta estática y el número de serie de este certificado TLS. Para obtener información detallada sobre estos parámetros, vea la Ayuda de Shell de administración de Lync Server escribiendo lo siguiente en el símbolo del sistema:
        
            Get-Help New-CsStaticRoute -Full
    
      - Para una conexión de Protocolo de control de transmisión (TCP), escriba el siguiente comando en el símbolo del sistema:
        

        > [!NOTE]
        > Si se especifica un nombre de dominio completo, primero debe configurar un registro A del Sistema de nombres de dominio (DNS).

        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        Por ejemplo:
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        Después se muestran los valores predeterminados de los parámetros opcionales de rutas estáticas:
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        Recomendamos encarecidamente no cambiar estos valores predeterminados. Sin embargo, si tuviera que cambiar alguno de estos parámetros, vea la Ayuda de Shell de administración de Lync Server escribiendo lo siguiente en el símbolo del sistema:
        
            Get-Help New-CsStaticRoute -Full

4.  Para mantener una ruta estática creada recientemente en el Almacén de administración central, ejecute una de las opciones siguientes, según corresponda:
    
    ```
    Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
    ```
    ```
    Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
    ```

## Vea también

#### Tareas

[Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

