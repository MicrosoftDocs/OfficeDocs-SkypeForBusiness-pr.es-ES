---
title: 'Lync Server 2013: Resumen de DNS-detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc30b787d938825f229f28b10d54907ad26a4d35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501327"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Resumen de DNS-detección automática en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-13_

La detección automática es un servicio flexible en el que aceptará la comunicación a través de HTTP o HTTPS. Para ello, el sistema de nombres de dominio (DNS) y los certificados que usan los servidores que hospedan el servicio Detección automática deben estar configurados correctamente. Los requisitos de certificado se tratan en [Resumen de certificado-detección automática en Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> La lógica de búsqueda DNS para los clientes de Lync Server usa un orden de resolución específico. Siempre debe incluir la lyncdiscoverinternal. &lt; domain &gt; y lyncdiscover. &lt; dominio &gt; en el DNS. Excluir lyncdiscoverinternal. &lt; &gt; el registro de dominio hará que los clientes internos no puedan conectarse a los servicios previstos o reciban la respuesta de detección automática incorrecta.



</div>

### <a name="internal-dns-records"></a>Registros DNS internos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nombre de host</th>
<th>Se resuelve en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal. &lt; nombre de dominio interno&gt;</p></td>
<td><p>El FQDN de servicios Web internos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, si IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt; nombre de dominio interno&gt;</p></td>
<td><p>Dirección IP de servicios Web internos (dirección IP virtual (VIP) si usa un equilibrador de carga) de su grupo de directores, si tiene uno o el grupo de servidores front-end si no tiene un director.</p></td>
</tr>
</tbody>
</table>


Debe crear uno de los siguientes registros DNS externos:

### <a name="external-dns-records"></a>Registros DNS externos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nombre de host</th>
<th>Se resuelve en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt; sipdomain&gt;</p></td>
<td><p>El FQDN de servicios web externos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, si IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt; sipdomain&gt;</p></td>
<td><p>Dirección IP externa o pública del proxy inverso.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> El tráfico externo circula a través del proxy inverso.



</div>

<div>


> [!NOTE]  
> Los clientes de dispositivos móviles no admiten varios certificados de capa de sockets seguros (SSL) de distintos dominios. Por lo tanto, la redirección de CNAME a distintos dominios no se admite a través de HTTPS. Por ejemplo, un registro CNAME de DNS para lyncdiscover.contoso.com que se redirige a una dirección de director.contoso.net no se admite a través de HTTPS. En una topología así, un cliente de dispositivo móvil necesita usar HTTP para la primera solicitud, de modo que la redirección de CNAME se resuelva a través de HTTP. A continuación, las solicitudes posteriores usan HTTPS. Para admitir este escenario, debe configurar el proxy inverso con una regla de publicación web para el puerto 80 (HTTP). Para obtener información detallada, consulte "para crear una regla de publicación web para el puerto 80" en <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the inverso proxy for Mobility in Lync Server 2013</A>. La redirección de CNAME al mismo dominio se admite a través de HTTPS. En este caso, el certificado del dominio de destino cubre el dominio de origen.



</div>

<div>

## <a name="see-also"></a>Consulte también


[Configuración del proxy inverso para movilidad en Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Resumen de certificado-detección automática en Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

