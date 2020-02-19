---
title: Resumen de DNS-servidor perimetral consolidado único con direcciones IP privadas con NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71395e8107c2a1fcb5bd999bd49ef73ea556fa13
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Resumen de DNS-servidor perimetral consolidado único con direcciones IP privadas que usan NAT en Lync Server 2013

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

Para evitar problemas de enrutamiento, compruebe que hay al menos dos adaptadores de red en los servidores perimetrales y que la puerta de enlace predeterminada solo está configurada en el adaptador de red asociado con la interfaz externa. Por ejemplo, como se muestra en la única topología perimetral consolidada que figura en el [perímetro consolidado único con direcciones IP privadas y NAT en Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), la puerta de enlace predeterminada apunta al firewall externo (10.45.16.1).

Puede configurar dos adaptadores de red en cada servidor perimetral de la siguiente forma:

  - **Adaptador de red 1 (interfaz interna)**
    
    Interfaz interna con 172.25.33.10 asignado.
    
    No se define ninguna puerta de enlace predeterminada.
    
    Asegúrese de que existe una ruta desde la red que contiene la interfaz perimetral interna a cualquier red que contenga servidores que ejecuten clientes de Lync Server 2013 o Lync Server 2013 (por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - **Adaptador de red 2 (Interfaz externa)**
    
    Se asignan tres direcciones IP privadas a este adaptador de red; por ejemplo 10.45.16.10 para el servidor perimetral de acceso, 10.45.16.20 para el servidor perimetral de conferencia web y 10.45.16.30 para el servidor perimetral AV.
    
    <div>
    

    > [!NOTE]
    > Es posible, aunque no se recomienda, usar una única dirección IP para las tres interfaces de servicios perimetrales. Aunque de este modo se ahorran direcciones IP, se requieren diferentes números de puerto para cada servicio. El número de puerto predeterminado es 443/TCP, que asegura que la mayoría de los firewalls remotos permitirán el tráfico. Cambiar los valores de los puertos a (por ejemplo) 5061/TCP para el servidor perimetral de acceso, 444/TCP para el servidor perimetral de conferencia web y 443/TCP para el servidor perimetral AV podría provocar problemas para usuarios remotos si están detrás de un firewall que no permite el tráfico sobre 5061/TCP y 444/TCP. Además, tres direcciones IP diferentes facilitan la resolución de problemas al poder filtrar sobre dirección IP.

    
    </div>
    
    La dirección IP perimetral de acceso es la principal, con la puerta de enlace predeterminada establecida en el enrutador integrado (10.45.16.1).
    
    Las direcciones IP perimetrales de A/V y de conferencia web son secundarias.

<div>


> [!TIP]
> La configuración del servidor perimetral con dos adaptadores de red es una de estas dos opciones. La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del servidor perimetral. La ventaja principal de esta opción es un adaptador de red distinto por cada servicio de servidor perimetral y, potencialmente, una recopilación de datos más concisa para la solución de problemas es necesaria



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a>Registros DNS necesarios para la topología perimetral consolidada con direcciones IP privadas que usan NAT (Ejemplo)

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
<td><p>Interfaz externa perimetral de acceso (Contoso). Repita según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p></td>
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
> Los registros que se enumeran en la tabla anterior se muestran con una extensión <EM>.net</EM> o <EM>.com</EM> para destacar en qué zona deben residir si no se utilizan DNS de partición de red. Si se utilizan DNS de partición de red, todos los registros estarán en la misma zona <EM>.com</EM>, con la única distinción de si están en la versión de zona DNS interna o externa. Para obtener más información, consulte "DNS de horizonte dividido" en <A href="lync-server-2013-determine-dns-requirements.md">determine los requisitos de DNS para Lync Server 2013</A>.



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

