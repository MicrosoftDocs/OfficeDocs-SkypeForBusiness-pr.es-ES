---
title: Resumen de DNS-servidor perimetral consolidado único con direcciones IP públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 622cb9811e33762bf40c05dfa5e5f0ab644b51aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Resumen de DNS-servidor perimetral consolidado único con direcciones IP públicas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-03-09_

Los requisitos de registro de DNS para el acceso remoto a Lync Server 2013 son bastante sencillos en comparación con los de certificados y puertos. Además, muchos registros son opcionales, en función de cómo configure los clientes que ejecutan Lync 2013 y si habilita la Federación.

Para obtener más información sobre los requisitos de DNS de Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obtener más información sobre la configuración automática de clientes que ejecutan Lync 2013 si no se ha configurado el DNS de cerebro dividido, consulte "configuración automática sin DNS de cerebro dividido" en [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

En la siguiente tabla se incluye un resumen de los registros DNS necesarios para admitir la topología perimetral consolidada de un solo equipo que se muestra en la figura Topología perimetral consolidada de un solo equipo. Tenga en cuenta que algunos registros DNS solo son necesarios para la configuración automática de clientes de Lync 2013 y Lync 2010. Si planea usar objetos de directiva de grupo (GPO) para configurar los clientes de Lync, los registros de configuración automática asociados no son necesarios.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisitos del adaptador de red del servidor perimetral

Para evitar problemas de enrutamiento, compruebe que hay al menos dos adaptadores de red en los servidores perimetrales y que la puerta de enlace predeterminada solo está configurada en el adaptador de red asociado con la interfaz externa. Por ejemplo, como se muestra en la topología perimetral consolidada única con direcciones IP públicas que figura en [un solo servidor perimetral consolidado con direcciones IP públicas en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), la puerta de enlace predeterminada apunta al enrutador externo del perímetro de Internet o del firewall que puede proporcionar direcciones IP públicas. La relación de red para las interfaces del servidor perimetral es una relación de ruta en lugar de una relación de NAT.

Puede configurar dos adaptadores de red en cada servidor perimetral de la siguiente forma:

  - **Adaptador de red 1 (interfaz interna)**
    
    Interfaz interna con 172.25.33.10 asignado.
    
    No se define ninguna puerta de enlace predeterminada.
    
    Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna a cualquier red que contenga servidores que ejecuten clientes de Lync Server 2013 o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - **Adaptador de red 2 (interfaz externa)**
    
    Tres direcciones IP privadas se asignan a este adaptador de red, por ejemplo 131.107.155.10 para el servidor perimetral de acceso, 131.107.155.20 para el servidor perimetral de conferencia web, 31.107.155.30 para el servidor perimetral AV
    
    <div>
    

    > [!NOTE]
    > Si bien no es recomendable, es posible usar una única dirección IP para las tres interfaces de servicio perimetral. Si bien esto no guarda las direcciones IP, requiere números de puerto diferentes para cada servicio. El número de puerto predeterminado es 443/TCP, que garantiza que la mayoría de los firewalls remotos permitirán el tráfico. Cambiar los valores del puerto a (por ejemplo) 5061/TCP para el Servidor perimetral de acceso, 444/TCP para el Servidor perimetral de conferencia web y 443/TCP para el servidor perimetral AV puede ocasionarle problemas a los usuarios remotos si se encuentran detrás de un firewall que no permite el tráfico por 5061/TCP y 444/TCP. Además, tres direcciones IP diferentes facilitan la solución de problemas ya que es posible filtrar la dirección IP.

    
    </div>
    
    La dirección IP pública de servidor perimetral de acceso es principal con puerta de enlace predeterminada establecida en el enrutador público (131.107.155.1).
    
    Las direcciones IP públicas de servidor perimetral de conferencia web y de A/V son direcciones IP adicionales en la sección **Avanzadas** de las propiedades de **Protocolo de Internet versión 4 (TCP/IPv4)** y **Protocolo de Internet versión 6 (TCP/IPv6)** de las **Propiedades de conexión de área local** en Windows Server.

<div>


> [!TIP]
> La configuración del servidor perimetral con dos adaptadores de red es una de estas dos opciones. La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del servidor perimetral. La ventaja principal de esta opción es un adaptador de red distinto por cada servicio de servidor perimetral y, potencialmente, una recopilación de datos más concisa para la solución de problemas es necesaria



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>Registros DNS necesarios para un servidor perimetral consolidado de un solo equipo con direcciones IP públicas (ejemplo)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/tipo/puerto</th>
<th>FQDN/Registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Se asigna a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Interfaz perimetral de acceso externa (Contoso) En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interfaz externa de servidor perimetral de conferencia web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externo</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interfaz externa de servidor perimetral de A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/SRV/443</p></td>
<td><p>_sip. _tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz perimetral de acceso externa. Necesario para la configuración automática de los clientes de Lync 2013 y Lync 2010 para que funcionen de forma externa. En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externo/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz perimetral externa de acceso SIP. Requerida para la detección DNS automática de socios federados conocidos como “Dominio SIP permitido” (denominada federación ampliada en versiones anteriores). En caso necesario, repita la operación para los dominios SIP con usuarios de Lync habilitados</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interfaz perimetral interna consolidada</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> Los registros enumerados en la tabla anterior se muestran con una extensión <EM>.net</EM> o bien <EM>.com</EM> para resaltar en qué zona deben residir si no va a usar el DNS de cerebro dividido. Si va a usar el DNS de cerebro dividido, todos los registros estarían en la misma zona con la única distinción de si están en la versión interna o en la externa. Para obtener más información, consulte "DNS de horizonte dividido" en <A href="lync-server-2013-determine-dns-requirements.md">determine los requisitos de DNS para Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="records-required-for-federation"></a>Registros requeridos para la federación


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/tipo/puerto</th>
<th>FQDN</th>
<th>Dirección IP/Registro de host FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz externa de SIP Access Edge requerida para la recuperación automática de DNS de su federación a otros posibles socios de la federación, y es conocida como “Dominios SIP permitidos” (llamados federación mejorada en versiones anteriores). Repita según sea necesario para todos los dominios SIP con usuarios habilitados por Lync</p>



> [!IMPORTANT]
> Este registro SRV se necesita para la movilidad y compensación de notificación de inserción

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Resumen DNS para el protocolo XMPP(Extensible Messaging y Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/tipo/puerto</th>
<th>FQDN</th>
<th>Dirección IP/Registro de host FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5269 externo</p></td>
<td><p>_xmpp-server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaz externa de proxy XMPP en el servicio perimetral de acceso o el grupo de servidores perimetrales. Repita los pasos necesarios para todos los dominios SIP internos con los usuarios habilitados para Lync donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio en la que se encuentra el usuario o la Directiva de usuario aplicada al Usuario habilitado para Lync. También debe configurarse un dominio XMPP permitido en la Directiva de socios federados XMPP. Vea los temas en <strong>vea también</strong> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>DNS externa/A</p></td>
<td><p>xmpp.contoso.com (por ejemplo)</p></td>
<td><p>Dirección IP del servicio perimetral de acceso en el servidor perimetral o el grupo de servidores perimetrales que hospedan el proxy XMPP</p></td>
<td><p>Señala el servicio perimetral de acceso o el grupo de servidores perimetrales que hospeda el servicio de proxy XMPP. Generalmente, el registro SRV que crea llevará a este registro de host (A o AAAA)</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

