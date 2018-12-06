---
title: "Resumen DNS - Servidor perimetral consolidado simple con direcciones IP públicas"
TOCTitle: Resumen DNS - Servidor perimetral consolidado simple con direcciones IP públicas
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48275778
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen DNS - Servidor perimetral consolidado simple con direcciones IP públicas en Lync Server 2013

 

_**Última modificación del tema:** 2017-03-09_

Los requisitos de registro DNS para tener acceso de manera remota a Lync Server 2013 son bastante sencillos en comparación con los de los certificados y los puertos. Además, muchos registros son opcionales, en función de cómo configure los clientes de Lync 2013 y de si habilita la federación.

Para más información sobre los requisitos de DNS de Lync 2013, vea [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obtener más información sobre la configuración automática de los clientes que ejecutan Lync 2013 cuando no está configurado el DNS de horizonte dividido, vea "Configuración automática sin DNS de horizonte dividido" en [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

En la siguiente tabla se incluye un resumen de los registros DNS que se requieren para admitir la topología perimetral consolidada de un solo equipo que se muestra en la figura Topología perimetral consolidada de un solo equipo. Tenga en cuenta que ciertos registros DNS solo se requieren para la configuración automática de clientes de Lync 2013 y Lync 2010. Si piensa usar objetos de directiva de grupo (GPO) para configurar clientes de Lync, los registros de configuración automáticos asociados no son necesarios.

## IMPORTANTE: requisitos de adaptador de red de Servidor perimetral

Para evitar problemas de enrutamiento, compruebe que hay, como mínimo, dos adaptadores de red en los Servidores perimetrales y que la puerta de enlace predeterminada está configurada solo en el adaptador de red asociado a la interfaz externa. Por ejemplo, como se muestra en la figura Topología perimetral consolidada de un solo equipo con direcciones IP públicas en [Topología perimetral consolidada de un solo equipo con direcciones IP públicas en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), la puerta de enlace predeterminada señalaría al enrutador externo en su perímetro de Internet o firewall que puede proporcionar una dirección IP pública. La relación de red para interfaces del Servidor perimetral es una relación de ruta en lugar de una relación NAT.

Puede configurar dos adaptadores de red en el servidor perimetral de la siguiente forma:

  - **Adaptador de red 1 (Interfaz interna)**
    
    Interfaz interna con 172.25.33.10 asignado.
    
    No se ha definido ninguna puerta de enlace predeterminada.
    
    Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna hasta todas las redes que contienen servidores que ejecutan clientes de Lync Server 2013 o Lync Server 2013 por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - **Adaptador de red 2 (Interfaz externa)**
    
    Tres direcciones IP privadas se asignan a este adaptador de red, por ejemplo 131.107.155.10 para el servidor perimetral de acceso, 131.107.155.20 para el servidor perimetral de conferencia web, 31.107.155.30 para el servidor perimetral AV
    

    > [!NOTE]
    > Es posible, aunque no se recomienda, usar una única dirección IP para las tres interfaces de servicios perimetrales. Aunque de este modo se ahorran direcciones IP, se requieren diferentes números de puerto para cada servicio. El número de puerto predeterminado es 443/TCP, que asegura que la mayoría de los firewalls remotos permitirán el tráfico. Cambiar los valores de los puertos a (por ejemplo) 5061/TCP para el servidor perimetral de acceso, 444/TCP para el servidor perimetral de conferencia web y 443/TCP para el servidor perimetral AV podría provocar problemas para usuarios remotos si están detrás de un firewall que no permite el tráfico sobre 5061/TCP y 444/TCP. Además, tres direcciones IP diferentes facilitan la resolución de problemas al poder filtrar sobre dirección IP.

    
    La dirección IP pública de servidor perimetral de acceso es principal con puerta de enlace predeterminada establecida en el enrutador público (131.107.155.1).
    
    Las direcciones IP públicas de servidor perimetral de conferencia web y de A/V son direcciones IP adicionales en la sección **Avanzadas** de las propiedades de **Protocolo de Internet versión 4 (TCP/IPv4)** y **Protocolo de Internet versión 6 (TCP/IPv6)** de las **Propiedades de conexión de área local** en Windows Server.

> [!TIP]  
> La configuración del Servidor perimetral con dos adaptadores de red es una de las dos opciones disponibles. La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del Servidor perimetral. La principal ventaja de esta opción es un adaptador de red distinto por servicio de Servidor perimetral, y es necesaria la recopilación de datos potencialmente más concisos al solucionar problemas.



### Registros DNS necesarios para un servidor perimetral consolidado de un solo equipo con direcciones IP públicas (ejemplo)

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
<td><p>131.107.155.10</p></td>
<td><p>Interfaz perimetral externa de acceso (Contoso). Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interfaz perimetral externa de conferencia web</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
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
<td><p>Interfaz externa perimetral de acceso SIP. Requerido para la detección DNS automática de socios federados conocidos como “Dominio SIP permitido” (denominado federación ampliada en versiones anteriores). Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interfaz perimetral interna consolidada</p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> Los registros enumerados en la tabla anterior se muestran con una extensión <em>.net</em> o bien <em>.com</em> para resaltar en qué zona deben residir si no va a usar el DNS de cerebro dividido. Si va a usar el DNS de cerebro dividido, todos los registros estarían en la misma zona con la única distinción de si están en la versión interna o en la externa. Para ver más información, consulte &quot;DNS de cerebro dividido&quot; en <a href="lync-server-2013-determine-dns-requirements.md">Determinar los requisitos DNS para Lync Server 2013</a>.



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
<td><p>Servidor perimetral de accesofea-avedge-service</p></td>
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

