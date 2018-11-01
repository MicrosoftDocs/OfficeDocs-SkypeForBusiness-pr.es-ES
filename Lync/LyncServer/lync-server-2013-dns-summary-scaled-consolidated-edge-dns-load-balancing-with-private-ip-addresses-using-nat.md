---
title: "Resumen DNS: Topol. perim. consol., equilib. carga DNS con IP privadas NAT"
TOCTitle: Resumen de DNS - Topologías perimetrales consolidadas escaladas, equilibrio de carga DNS con direcciones IP privadas con NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48274479
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de DNS - Topologías perimetrales consolidadas escaladas, equilibrio de carga DNS con direcciones IP privadas con NAT en Lync Server 2013

 

_**Última modificación del tema:** 2017-03-09_

Los requisitos de registro DNS para tener acceso de manera remota a Lync Server 2013 son bastante sencillos en comparación con los de los certificados y los puertos. Además, muchos registros son opcionales, en función de cómo configure los clientes de Lync 2013 y de si habilita la federación.

Para más información sobre los requisitos de DNS de Lync 2013, vea [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para más información sobre la configuración automática de clientes de Lync 2013 si no está configurado el DNS de cerebro dividido, consulte “Configuración automática sin DNS de cerebro dividido” en [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

En la siguiente tabla se incluye un resumen de los registros DNS que se necesitan para admitir la topología perimetral consolidada de un solo equipo que se muestra en la figura Topología perimetral consolidada de un solo equipo. Tenga en cuenta que ciertos registros DNS solo se necesitan para la configuración automática de clientes de Lync 2013. Si piensa usar objetos de directiva de grupo (GPO) para configurar clientes de Lync los registros asociados no son necesarios.

## IMPORTANTE: requisitos de adaptador de red de Servidor perimetral

Para evitar problemas de redirección, compruebe que haya, como mínimo, dos adaptadores de red en los Servidores perimetrales y que la puerta de enlace predeterminada esté configurada solo en el adaptador de red asociado a la interfaz externa. Por ejemplo, como se muestra en la figura Escenario perimetral consolidado escalado en [Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), la puerta de enlace predeterminada apuntaría al firewall externo.

Puede configurar dos adaptadores de red en cada servidor perimetral de la siguiente forma

  - **Adaptador de red 1 - Nodo 1 (Interfaz interna)**
    
    Interfaz interna con 172.25.33.10 asignado.
    
    No se ha definido ninguna puerta de enlace predeterminada.
    
    Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna hasta todas las redes que contienen servidores que ejecutan clientes de Lync Server 2013 o Lync Server 2013 por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - **Adaptador de red 1 - Nodo 2 (Interfaz interna)**
    
    Interfaz interna con 172.25.33.11 asignada.
    
    No se ha definido ninguna puerta de enlace predeterminada.
    
    Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna hasta todas las redes que contienen servidores que ejecutan clientes de Lync Server 2013 o Lync Server 2013 por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - **Adaptador de red 2 - Nodo 1 (Interfaz externa)**
    
    Se asignan tres direcciones IP privadas a este adaptador de red; por ejemplo 10.45.16.10 para el servidor perimetral de acceso, 10.45.16.20 para el servidor perimetral de conferencia web, 10.45.16.30 para el servidor perimetral de AV.
    

    > [!NOTE]
    > Es posible, aunque no se recomienda, usar una única dirección IP para las tres interfaces de servicios perimetrales. Aunque de este modo se ahorran direcciones IP, se requieren diferentes números de puerto para cada servicio. El número de puerto predeterminado es 443/TCP, que asegura que la mayoría de los firewalls remotos permitirán el tráfico. Cambiar los valores de los puertos a (por ejemplo) 5061/TCP para el servidor perimetral de acceso, 444/TCP para el servidor perimetral de conferencia web y 443/TCP para el servidor perimetral AV podría provocar problemas para usuarios remotos si están detrás de un firewall que no permite el tráfico sobre 5061/TCP y 444/TCP. Además, tres direcciones IP diferentes facilitan la resolución de problemas al poder filtrar sobre dirección IP.

    
    La dirección IP pública de servidor perimetral de acceso es principal con puerta de enlace predeterminada establecida en el enrutador público (10.45.16.1).
    
    Las direcciones IP perimetrales privadas de conferencia web y de A/V son direcciones IP adicionales en la sección **Avanzadas** de las propiedades de **Protocolo de Internet versión 4 (TCP/IPv4)** y **Protocolo de Internet versión 6 (TCP/IPv6)** de las **Propiedades de conexión de área local** en Windows Server.

  - **Adaptador de red 2 - Nodo 2 (Interfaz externa)**
    
    Tres direcciones IP privadas se asignan a este adaptador de red, por ejemplo 10.45.16.11 para el servidor perimetral de acceso, 10.45.16.21 para el servidor perimetral de conferencia web, 10.45.16.31 para el servidor perimetral AV.
    
    La dirección IP pública de servidor perimetral de acceso es principal con puerta de enlace predeterminada establecida en el enrutador público (10.45.16.1).
    
    Las direcciones IP perimetrales privadas de conferencia web y de A/V son direcciones IP adicionales en la sección **Avanzadas** de las propiedades de **Protocolo de Internet versión 4 (TCP/IPv4)** y **Protocolo de Internet versión 6 (TCP/IPv6)** de las **Propiedades de conexión de área local** en Windows Server.

> [!TIP]  
> La configuración del Servidor perimetral con dos adaptadores de red es una de las dos opciones disponibles. La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del Servidor perimetral. La principal ventaja de esta opción es un adaptador de red distinto por servicio de Servidor perimetral, y es necesaria la recopilación de datos potencialmente más concisos al solucionar problemas.



### Registros DNS requeridos para el servidor perimetral consolidado escalado, carga de DNS equilibrada con direcciones IP privadas que usan NAT (ejemplo)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN/Registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 y 131.107.155.11</p></td>
<td><p>Interfaz perimetral externa de acceso (Contoso). Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 y 131.107.155.21</p></td>
<td><p>Interfaz perimetral externa de conferencia web</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 y 131.107.155.31</p></td>
<td><p>Interfaz perimetral externa A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz externa perimetral de acceso. Requerido para la configuración automática de clientes de Lync 2013 y Lync 2010 que trabajen externamente. Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externo</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz perimetral externa de acceso SIP. Requerida para la detección DNS automática de socios federados conocidos como “Dominio SIP permitido” (denominada federación ampliada en versiones anteriores). En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 y 172.25.33.11</p></td>
<td><p>Interfaz perimetral interna consolidada</p></td>
</tr>
</tbody>
</table>


## Registros necesarios para la federación


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN</th>
<th>Dirección IP/Registro de host FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz perimetral externa de acceso SIP Requerida para detección automática DNS de su federación a otros posibles socios de federación, que se conocen como “Dominios SIP permitidos” o &quot;federación ampliada&quot; en versiones anteriores). Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p>
<div>

> [!IMPORTANT]  
> Este registro de SRV es necesario para fines de movilidad y para el centro de enrutamiento de notificaciones de inserción


</div></td>
</tr>
</tbody>
</table>


## Resumen de DNS – Conectividad de mensajería instantánea pública


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN/Registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Servidor perimetral de acceso</p></td>
<td><p>Interfaz perimetral externa de acceso (Contoso). Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p></td>
</tr>
</tbody>
</table>


## Resumen de DNS para el protocolo extensible de mensajería y presencia


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/TIPO/Puerto</th>
<th>FQDN</th>
<th>Dirección IP/Registro de host FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>La interfaz externa de proxy XMPP del Servidor perimetral de acceso o Grupo de servidores perimetrales. Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync en los que se permita el contacto con contactos XMPP configurando la directiva de acceso externo mediante una directiva global, directiva del sitio donde se encuentre el usuario o directiva de usuario aplicada al usuario habilitado para Lync. También debe configurarse un dominio XMPP permitido en la directiva Socios federados de XMPP. Para obtener más información, vea los temas de <strong>Consulte también</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>xmpp.contoso.com (por ejemplo)</p></td>
<td><p>Dirección IP del Servidor perimetral de acceso en el Servidor perimetral o el Grupo de servidores perimetrales que hospeda el proxy de XMPP</p></td>
<td><p>Apunta al Servidor perimetral de acceso o al Grupo de servidores perimetrales que hospeda el servicio de proxy de XMPP. Normalmente el registro SRV que crea apuntará a este registro host (A o AAAA)</p></td>
</tr>
</tbody>
</table>

