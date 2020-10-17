---
title: Resumen de certificado-SIP, Federación XMPP y mensajería instantánea pública
description: 'Resumen de certificado: SIP, Federación XMPP y mensajería instantánea pública.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565d3b935d304aa09588688bd8d71948b1b3ec3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572146"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumen de certificado: SIP, Federación XMPP y mensajería instantánea pública en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-15_

Los certificados que se necesitan para federar con Microsoft Lync Server 2013, Lync Server 2010 y Office Communications Server se suelen cumplir con los certificados que configure, solicite y asigne a su servidor perimetral.

Los requisitos de certificado para habilitar y establecer comunicaciones con los asociados del protocolo extensible de mensajería y presencia (XMPP) requieren la adición de entradas para los dominios XMPP. El registro incluido en el certificado como nombre alternativo del firmante (SAN) será el dominio que puede participar en las comunicaciones XMPP. El dominio puede ser el dominio de nivel de raíz (por ejemplo, contoso.com) si desea habilitar XMPP para todo el dominio, o bien dominios secundarios seleccionados (por ejemplo, corp.contoso.com, finance.contoso.com) si desea habilitar XMPP para un subconjunto de usuarios.

Para configurar certificados para la conectividad de mensajería instantánea pública, tenga en cuenta que no hay nada diferente de otros tipos de Federación SIP o de certificados de servidor perimetral estándar, excepto que America Online (AOL) requiere el certificado o los certificados (en el caso de un grupo de servidores perimetrales) que también contengan el EKU de cliente. El EKU de cliente es una adición al certificado y forma parte del certificado público externo que se asigna a su servidor perimetral.

Para confirmar que ha cumplido los requisitos de certificado correctos para la implementación del servidor perimetral, revise los temas que se enumeran en la sección **vea también**.

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
<th>Nombre de sujeto</th>
<th>Nombres alternativos del sujeto (SAN)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor perimetral de acceso/externo</p></td>
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
<li><p>Servicio perimetral de conferencias web</p></li>
<li><p>Servicio perimetral A/V</p></li>
</ul>



> [!NOTE]
> Técnicamente, no se asigna un certificado al servidor perimetral a/V. La comunicación y la autenticación seguras se administran mediante el servicio de autenticación relé multimedia (MRAS). MRAS usa el certificado asignado a la interfaz interna del servidor perimetral.


<p>Tenga en cuenta que las SAN se agregan automáticamente al certificado basado en las definiciones del Generador de topologías. Agregue entradas SAN según sea necesario para dominios adicionales de SIP y otras entradas que necesite admitir. El nombre del sujeto se replica en la SAN y debe estar presente para el correcto funcionamiento.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Consulte también


[Configuración XMPP de ejemplo en Lync Server 2013: Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planeación de certificados de servidor perimetral en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Resumen de certificado-perímetro consolidado de un solo consolidado con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Resumen de certificado-perímetro consolidado de un solo consolidado con direcciones IP públicas en Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Resumen de certificado-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP privadas mediante NAT en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Resumen de certificado-servidor perimetral consolidado ampliado, equilibrio de carga DNS con direcciones IP públicas en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Resumen de certificado-servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

