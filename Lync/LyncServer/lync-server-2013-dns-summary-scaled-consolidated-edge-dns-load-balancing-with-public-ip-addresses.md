---
title: "Resumen DNS: Servidor perimetral consol. ampliado, equilib. carga DNS con IP públicas"
TOCTitle: Resumen de DNS - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48276906
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumen de DNS - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013

 

_**Última modificación del tema:** 2017-03-09_

Los requisitos de registro DNS para tener acceso de manera remota a Lync Server 2013 son bastante sencillos en comparación con los de los certificados y los puertos. Además, muchos registros son opcionales, en función de cómo configure los clientes de Lync 2013 y de si habilita la federación.

Para más información sobre los requisitos de DNS de Lync 2013, vea [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para más información sobre la configuración automática de clientes de Lync 2013 si no está configurado el DNS de cerebro dividido, consulte “Configuración automática sin DNS de cerebro dividido” en [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

En la siguiente tabla se incluye un resumen de los registros DNS que se necesitan para admitir la topología perimetral consolidada de un solo equipo que se muestra en la figura Topología perimetral consolidada de un solo equipo. Tenga en cuenta que ciertos registros DNS solo se necesitan para la configuración automática de clientes de Lync 2013. Si piensa usar objetos de directiva de grupo (GPO) para configurar clientes de Lync los registros asociados no son necesarios.

## IMPORTANTE: requisitos de adaptador de red de Servidor perimetral

Para evitar problemas de redirección, compruebe que haya, como mínimo, dos adaptadores de red en los Servidores perimetrales y que la puerta de enlace predeterminada esté configurada solo en el adaptador de red asociado a la interfaz externa. Por ejemplo, como se muestra en la figura Escenario perimetral consolidado escalado en [Perímetro consolidado escalado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md), la puerta de enlace predeterminada apuntaría al firewall externo.

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
    
    Tres direcciones IP privadas se asignan a este adaptador de red, por ejemplo 131.107.155.10 para el Servidor perimetral de acceso, 131.107.155.20 para el Servicio perimetral de conferencia web, 131.107.155.30 para el Servicio perimetral A/V.
    
    La dirección IP pública de Servidor perimetral de acceso es principal con puerta de enlace predeterminada establecida en el enrutador público (131.107.155.1).
    
    Las direcciones IP privadas de Servicio perimetral de conferencia web y de Servicio perimetral A/V son direcciones IP adicionales de la sección **Avanzadas** de las propiedades de **Protocolo de Internet versión 4 (TCP/IPv4)** y **Protocolo de Internet versión 6 (TCP/IPv6)** de las **Propiedades de conexión de área local** en Windows Server.
    

    > [!NOTE]
    > Aunque no lo recomendamos, es posible usar una sola dirección IP para las tres interfaces de servicio perimetral. Si bien esto guarda las direcciones IP, se necesitan números de puerto diferentes para cada servicio. El número de puerto predeterminado es 443/TCP, que garantiza que la mayoría de los firewalls remotos permitirán el tráfico. Cambiar los valores del puerto a (por ejemplo) 5061/TCP para el Servidor perimetral de acceso, 444/TCP para el Servicio perimetral de conferencia web y 443/TCP para el Servicio perimetral A/V puede ocasionarle problemas a los usuarios remotos si se encuentran detrás de un firewall que no permite el tráfico por 5061/TCP y 444/TCP. Además, tres direcciones IP diferentes facilitan la solución de problemas ya que es posible filtrar la dirección IP.



  - **Adaptador de red 2 - Nodo 2 (Interfaz externa)**
    
    Tres direcciones IP privadas se asignan a este adaptador de red, por ejemplo 131.107.155.11 para el Servidor perimetral de acceso, 131.107.155.21 para el Servicio perimetral de conferencia web y 131.107.155.31 para el Servicio perimetral A/V.
    
    La dirección IP pública de Servidor perimetral de acceso es principal con puerta de enlace predeterminada establecida en el enrutador público (131.107.155.1).
    
    Las direcciones IP privadas de Servicio perimetral de conferencia web y de Servicio perimetral A/V son direcciones IP adicionales de la sección **Avanzadas** de las propiedades de **Protocolo de Internet versión 4 (TCP/IPv4)** y **Protocolo de Internet versión 6 (TCP/IPv6)** de las **Propiedades de conexión de área local** en Windows Server.

> [!TIP]  
> La configuración del Servidor perimetral con dos adaptadores de red es una de las dos opciones disponibles. La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del Servidor perimetral. La principal ventaja de esta opción es un adaptador de red distinto por servicio de Servidor perimetral, y es necesaria la recopilación de datos potencialmente más concisos al solucionar problemas.



### Registros DNS necesarios para una topología perimetral consolidada escalada, equilibrio de carga de DNS con direcciones IP públicas (ejemplo)

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
<td><p>Interfaz externa del Servidor perimetral de acceso (Contoso) Repita tantas veces como sea necesario para todos los dominios SIP con usuarios de Lync habilitados</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 y 131.107.155.21</p></td>
<td><p>Interfaz externa de Servicio perimetral de conferencia web</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 y 131.107.155.31</p></td>
<td><p>Servicio perimetral A/Vfea-webconfedge-service</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/SRV/443</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz externa de Servidor perimetral de acceso. Necesaria para la configuración automática de clientes de Lync 2013 y Lync 2010 para que trabajen de manera externa. Repita tantas veces como sea necesario para todos los usuarios de Lync habilitados.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externo</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz externa de Servidor perimetral de acceso. Necesaria para la detección DNS automática de socios federados conocidos como “Dominio SIP permitido” (denominada federación ampliada en versiones anteriores). Repita tantas veces como sea necesario para todos los dominios SIP con usuarios habilitados de Lync</p></td>
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
<td><p>Interfaz externa del Servidor perimetral de acceso SIP. Necesaria para la detección automática DNS de su federación ante los posibles socios de federación. Conocida como “Dominios SIP permitidos” (denominado federación ampliada en versiones anteriores).</p>
<div>

> [!IMPORTANT]  
> Repita tantas veces como sea necesario para todos los dominios SIP con usuarios habilitados para Lync y clientes de Microsoft Lync Mobile que usen el Servicios de notificaciones de inserción o el Servicios de notificaciones de inserción de Apple


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
<td><p>Interfaz externa del Servidor perimetral de acceso (Contoso) Repita tantas veces como sea necesario para todos los dominios SIP con usuarios de Lync habilitados</p></td>
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
<td><p>Interfaz externa de proxy XMPP en el Servidor perimetral de acceso o el Grupo de servidores perimetrales. Repita tantas veces como sea necesario para todos los dominios SIP internos con usuarios de Lync habilitados, donde el contacto con contactos XMPP se permite por medio de la configuración de la directiva de acceso externo, una directiva global, una directiva del sitio donde se encuentra el usuario o una directiva de usuario aplicada al usuario de Lync habilitado. Configure también un dominio de XMPP permitido en la directiva de socios federados de XMPP. Vea los temas de <strong>Vea también</strong> para más información</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>xmpp.contoso.com (por ejemplo)</p></td>
<td><p>Dirección IP del Servidor perimetral de acceso en el Servidor perimetral o el Grupo de servidores perimetrales que hospeda el proxy de XMPP</p></td>
<td><p>Apunta al Servidor perimetral de acceso o al Grupo de servidores perimetrales que hospeda el servicio de proxy de XMPP. Normalmente el registro SRV que crea apuntará a este registro host (A o AAAA)</p></td>
</tr>
</tbody>
</table>

