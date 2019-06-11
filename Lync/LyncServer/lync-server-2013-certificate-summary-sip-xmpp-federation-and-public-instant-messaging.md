---
title: 'Resumen del certificado: SIP, Federación XMPP y mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dccb46b9f2b6d934f1cd0960bb11a369fb585ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumen del certificado: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-15_

Los certificados que necesita para la Federación con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server generalmente se cumplirán con los certificados que configure, solicite y asigne a su servidor perimetral.

Los requisitos de certificados para habilitar y establecer comunicaciones con los partners protocolo de presencia y mensajería extensible (XMPP) requieren agregar entradas a los dominios XMPP. El registro que se incluye en el certificado como un nombre alternativo del sujeto (SAN) será el dominio que puede participar en las comunicaciones XMPP. El dominio puede ser el dominio de nivel raíz (por ejemplo, contoso.com) Si desea habilitar XMPP para todo el dominio o puede seleccionar dominios secundarios (por ejemplo, corp.contoso.com, finance.contoso.com) si va a habilitar XMPP para un subconjunto de usuarios.

Para configurar certificados para la conectividad de mensajería instantánea pública, tenga en cuenta que no hay nada diferente de otros tipos de Federación SIP o incluso de certificados de servidor perimetral estándar, excepto en que America Online (AOL) requiere el certificado o certificados (en el caso de un grupo perimetral) para contener también el EKU de cliente. El EKU de cliente es una adición al certificado y forma parte del certificado público externo que se asigna al servidor perimetral.

Para confirmar que ha cumplido los requisitos de certificado correctos para su implementación del servidor perimetral, revise los temas que aparecen en la sección titulada **también**.

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nombre del asunto</th>
<th>Nombres alternativos de asunto (SAN)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Perimetral de acceso externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Para admitir el espacio de nombres XMPP de contoso.com


<p>sip.fabrikam.com</p>



> [!NOTE]
> Para admitir el espacio de nombres SIP fabrikam.com


<p>fabrikam.com</p>



> [!NOTE]
> Para admitir el espacio de nombres XMPP de fabrikam.com

</td>
<td><p>El certificado debe ser de una entidad de certificación pública y debe tener el EKU de servidor y el EKU de cliente si se va a implementar la conectividad de mensajería instantánea pública con AOL. El certificado se asigna a las interfaces del servidor perimetral externo para:</p>
<ul>
<li><p>Servicio perimetral de acceso</p></li>
<li><p>Servicio perimetral de conferencia web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>



> [!NOTE]
> Técnicamente, no se asigna un certificado al borde de A/V. La comunicación y la autenticación seguras se administran mediante el servicio de autenticación de retransmisión multimedia (MRAS). MRAS usa el certificado asignado a la interfaz interna del servidor perimetral.


<p>Tenga en cuenta que las redes San se agregan automáticamente al certificado según sus definiciones en el generador de topologías. Agregue las entradas de SAN según sea necesario para dominios SIP adicionales y otras entradas que necesite admitir. El nombre del asunto se replica en el SAN y debe estar presente para que funcione correctamente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Resumen de certificado - Servidor perimetral consolidado simple con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Resumen de certificado - Perímetro consolidado de equipo único con direcciones IP públicas en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Resumen de certificado - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas con NAT en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[Resumen de certificado - Servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Resumen de certificado - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

