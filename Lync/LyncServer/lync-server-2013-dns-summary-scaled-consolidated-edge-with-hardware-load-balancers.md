---
title: Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d411b004edde96314e3c06d7f28a9f9d294688ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Resumen DNS - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-27_

Los requisitos de registro DNS para el acceso remoto a Lync Server 2013 son bastante sencillos en comparación con los de certificados y puertos. Además, muchos registros son opcionales, en función de cómo configure los clientes que ejecutan Lync 2013 y si habilita la Federación.

Para obtener más información sobre los requisitos de DNS de Lync 2013, consulte [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obtener más información sobre cómo configurar la configuración automática de los clientes de Lync 2013, si no se ha configurado el servidor DNS de horizonte dividido, consulte la sección "configuración automática sin DNS de división de datos" en [determinar los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

La tabla siguiente contiene un resumen de los registros DNS necesarios para admitir la figura de topología de perímetro consolidado escalado (equilibrio de carga de hardware). Tenga en cuenta que algunos registros DNS solo son necesarios para la configuración automática para clientes de Lync. Si planea usar objetos de directiva de grupo (GPO) para configurar clientes de Lync, los registros asociados no son necesarios.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisitos del adaptador de red del servidor perimetral

Para evitar problemas de enrutamiento, compruebe que hay al menos dos adaptadores de red en los servidores perimetrales y que la puerta de enlace predeterminada solo está configurada en el adaptador de red asociado a la interfaz externa. Por ejemplo, tal y como se muestra en el escenario de borde consolidado escalado en el [borde consolidado escalado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), la puerta de enlace predeterminada apunta al firewall externo.

Puede configurar dos adaptadores de red en cada uno de los servidores perimetrales de la siguiente manera:

  - **Adaptador de red 1 (interfaz interna)**
    
    Interfaz interna con 172.25.33.10 asignado.
    
    No hay puerta de enlace predeterminada.
    
    Asegúrese de que haya una ruta desde la red que contenga la interfaz interna del servidor perimetral a cualquier red que contenga clientes de Lync Server o servidores que ejecuten Lync Server (por ejemplo, de 172.25.33.0 a 192.168.10.0).

  - **Adaptador de red 2 (interfaz externa)**
    
    Se asignan tres direcciones IP públicas a este adaptador de red, por ejemplo, 131.107.155.10 para el servicio perimetral de acceso, 131.107.155.20 para el servicio perimetral de conferencias web, 131.107.155.30 para el servicio perimetral A/V.
    
    <div>
    

    > [!NOTE]
    > Las direcciones IP que se asignan a las interfaces de red externas reales del servidor perimetral pueden depender del equilibrador de carga de hardware que elija. Consulte la documentación de su equilibrador de carga de hardware para conocer los requisitos de las direcciones IP reales.<BR>Es posible, aunque no recomendable, usar una única dirección IP para las tres interfaces de servicio perimetral. Aunque esto sí guarda las direcciones IP, requiere números de Puerto diferentes para cada servicio. El número de puerto predeterminado es 443/TCP, lo que garantiza que la mayoría de los firewalls remotos permitan el tráfico. Cambiar los valores del puerto a (por ejemplo) 5061/TCP para el servicio perimetral de acceso, 444/TCP para el servicio perimetral de las conferencias web y 443/TCP para el servicio perimetral a/V puede causar problemas a los usuarios remotos en los que un firewall que estén detrás no permite el tráfico por 5061/TCP y 444/TCP. Además, tres direcciones IP distintas hacen que la solución de problemas sea más fácil, ya que es posible filtrar por dirección IP.

    
    </div>
    
    La dirección IP del servicio perimetral de acceso es principal con la puerta de enlace predeterminada establecida para enrutador orientado a Internet (131.107.155.1).
    
    Servicio perimetral de conferencias web y direcciones IP del servicio de borde A/V secundarios.

<div>


> [!TIP]
> La configuración del servidor perimetral con dos adaptadores de red es una de dos opciones. La otra opción es usar un adaptador de red para el lado interno y tres adaptadores de red para el lado externo del servidor perimetral. La principal ventaja de esta opción es un adaptador de red distinto por cada servicio de servidor perimetral, así como una recopilación de datos potencialmente más concisa cuando se necesita la solución de problemas.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>Registros DNS necesarios para el límite consolidado con escala, equilibrio de carga de hardware (ejemplo)

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
<th>FQDN/registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Se asigna a/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externo/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Interfaz externa de servicio perimetral de acceso (contoso). Repetir según sea necesario para todos los dominios SIP con usuarios habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interfaz externa de servicio perimetral de conferencia Web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externo/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interfaz externa de servicio perimetral A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS/SRV/443 externo</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interfaz externa de servicio perimetral de acceso. Necesario para que la configuración automática de los clientes de Lync 2013 y Lync 2010 funcione de forma externa. Repita el procedimiento según sea necesario para todos los dominios SIP con usuarios habilitados para Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externo/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Servicio perimetral de acceso SIP interfaz externa necesaria para la detección automática de DNS de los socios federados conocidos como "dominio SIP permitido" (denominado Federación mejorada en versiones anteriores). Repita el procedimiento según sea necesario para todos los dominios SIP con usuarios habilitados para Lync y los clientes móviles de Microsoft Lync que usan el servicio de notificaciones Push o el servicio de notificaciones push de Apple</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interfaz interna de Edge consolidado</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

