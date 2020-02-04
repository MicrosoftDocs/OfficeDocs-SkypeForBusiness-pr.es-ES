---
title: 'Resumen de puertos: Federación protocolo de presencia y mensajería extensible (XMPP)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a18129fce98b3bb9bc613f4fc752daadfb6c5ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Resumen de puertos: Federación protocolo de presencia y mensajería extensible (XMPP) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Los puertos y protocolos definidos para el proxy protocolo de presencia y mensajería extensible (XMPP) implementado en el servidor perimetral permiten las comunicaciones del socio XMPP federado hasta el servidor perimetral, y también permiten la comunicación desde el servidor perimetral al XMPP socio federado. Una regla también se define en el Firewall de orientación interna desde el servidor front-end o el grupo front-end hasta el servidor perimetral o el grupo Edge.

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Resumen de Firewall para el protocolo de presencia y mensajería extensible


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP o UDP/puerto</th>
<th>Origen (dirección IP)</th>
<th>Destino (dirección IP)</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección IP de la interfaz de servicio perimetral de Access</p></td>
<td><p>Puerto de comunicación de servidor a servidor estándar para XMPP. Permite la comunicación con el proxy XMPP del servidor perimetral de socios de XMPP</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Dirección IP de la interfaz de servicio perimetral de Access</p></td>
<td><p>Cualquiera</p></td>
<td><p>Puerto de comunicación de servidor a servidor estándar para XMPP. Permite la comunicación desde el proxy XMPP del servidor perimetral a socios XMPP de Federación</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Cualquiera</p></td>
<td><p>IP de la interfaz del servidor perimetral interno</p></td>
<td><p>Tráfico de XMPP interno de la puerta de enlace XMPP del servidor front-end o del grupo front-end al servidor perimetral</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

