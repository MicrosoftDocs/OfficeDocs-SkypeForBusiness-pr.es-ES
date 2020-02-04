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
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Resumen de DNS-detección automática en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-13_

Detección automática es un servicio flexible, ya que acepta la comunicación a través de HTTP o HTTPS. Para ello, el sistema de nombres de dominio (DNS) y los certificados usados por los servidores que hospedan el servicio Detección automática deben estar configurados correctamente. Los requisitos de certificado se tratan en [Resumen del certificado: detección automática en Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> La lógica de búsqueda DNS para los clientes de Lync Server usa un orden específico de resolución. Siempre debes incluir el lyncdiscoverinternal. &lt;dominio&gt; y el lyncdiscover. &lt;dominio&gt; en el DNS. Excluyendo la lyncdiscoverinternal. &lt;Registro&gt; de dominio hará que los clientes internos no se conecten a los servicios previstos o reciban la respuesta incorrecta de detección automática.



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
<td><p>Lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</p></td>
<td><p>El FQDN de los servicios Web internos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, si IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt;nombre de dominio interno&gt;</p></td>
<td><p>Dirección IP de los servicios Web internos (dirección IP virtual (VIP) si usa un equilibrador de carga) de su grupo de directores, si tiene uno o el grupo de servidores front-end, si no tiene un director.</p></td>
</tr>
</tbody>
</table>


Cree uno de los siguientes registros de DNS externos:

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
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>El FQDN de servicios web externos para el grupo de directores, si tiene uno, o para el grupo de servidores front-end si no tiene un director.</p></td>
</tr>
<tr class="even">
<td><p>A (host, si IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Dirección IP externa o pública del proxy inverso.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> El tráfico externo pasa por el proxy inverso.



</div>

<div>


> [!NOTE]  
> Los clientes de dispositivos móviles no admiten varios certificados de capa de sockets seguros (SSL) de diferentes dominios. Por lo tanto, no se admite la redirección CNAME a dominios diferentes a través de HTTPS. Por ejemplo, un registro CNAME de DNS para lyncdiscover.contoso.com que redirige a una dirección de director.contoso.net no es compatible con HTTPS. En una topología de este tipo, un cliente de dispositivo móvil debe usar HTTP para la primera solicitud, de modo que la redirección CNAME se resuelva por HTTP. Después, las solicitudes posteriores usan HTTPS. Para admitir este escenario, debe configurar el proxy inverso con una regla de publicación web para el puerto 80 (HTTP). Para obtener más información, consulte "para crear una regla de publicación web para el puerto 80" en <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurar el proxy inverso para la movilidad en Lync Server 2013</A>. El redireccionamiento CNAME para el mismo dominio es compatible con HTTPS. En este caso, el certificado del dominio de destino cubre el dominio de origen.



</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración del proxy inverso para movilidad en Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Resumen del certificado: detección automática en Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

