---
title: 'Lync Server 2013: Resumen de certificado-Federación de protocolo de presencia y mensajería extensible (XMPP)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af2c226397c5225fc26f6dbdf40d12a4bdb1ca0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Resumen de certificados: Federación de protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-23_

Los requisitos de certificados para habilitar y establecer comunicaciones con los partners de protocolo de presencia y mensajería extensible (XMPP) requieren el registro adicional de los dominios XMPP. El registro que se incluye en el certificado como un nombre alternativo del sujeto (SAN) será el dominio que puede participar en las comunicaciones XMPP. El dominio puede ser el dominio de nivel raíz (por ejemplo, contoso.com) Si desea habilitar XMPP para todo el dominio o puede seleccionar dominios secundarios (por ejemplo, corp.contoso.com, finance.contoso.com) si va a habilitar XMPP para un subconjunto de usuarios.

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Resumen del certificado para el protocolo de presencia y mensajería extensible


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
<th>Nombres alternativos de asunto (SAN)/Order</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Asignar a servicio perimetral de acceso al servidor perimetral o grupo de servidores perimetrales</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>Las tres primeras entradas de SAN son las entradas normales de SAN para un servidor de borde completo. La contoso.com es la entrada necesaria para la Federación con el socio XMPP en el nivel de dominio raíz. Esta entrada permitirá que XMPP para todos los dominios con el sufijo contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  


[Configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Solicitud-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

