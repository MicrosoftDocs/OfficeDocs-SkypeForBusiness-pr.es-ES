---
title: 'Resumen de DNS: Federación protocolo de presencia y mensajería extensible (XMPP)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff58998ef9114baeb7dc7c6462ca0ebaae114f10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Resumen de DNS: Federación protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-08_

Para configurar el protocolo de presencia y mensajería extensible (XMPP) para su implementación, debe crear dos registros del sistema de nombres de dominio (DNS) en un servidor DNS externo que resuelva los registros para el servicio perimetral de acceso de su servidor perimetral o de grupo perimetral.

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Resumen de DNS para el protocolo de presencia y mensajería extensible


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
<th>Dirección IP/registro de host FQDN</th>
<th>Se asigna a/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5269 externo</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interfaz externa de proxy XMPP en el servicio perimetral de acceso o grupo perimetral. Repita el procedimiento según sea necesario para todos los dominios SIP internos con los usuarios habilitados para Lync donde se permite el contacto con los contactos XMPP a través de la configuración de la Directiva de acceso externo a través de una directiva global, una directiva de sitio donde se encuentra el usuario o la Directiva de usuario aplicada al Usuario habilitado para Lync. También se debe configurar un dominio XMPP permitido en la Directiva del socio XMPP federado. Vea temas en <strong>vea también</strong> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>DNS externo/A</p></td>
<td><p>xmpp.contoso.com (por ejemplo)</p></td>
<td><p>Dirección IP del servicio perimetral de acceso en el servidor perimetral o grupo perimetral que aloja el proxy XMPP</p></td>
<td><p>Señala el servicio perimetral de Access o el grupo de límites que alberga el servicio de proxy XMPP. Normalmente, el registro SRV que cree apuntará a este registro de host (A o AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar la federación XMPP en Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  


[Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

