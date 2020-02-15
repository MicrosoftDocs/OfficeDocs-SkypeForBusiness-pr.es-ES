---
title: 'Lync Server 2013: Resumen de Puerto-grupo de Director escalado, equilibrador de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18c0957d66d9b877a67819b8fd8d46d4e614cdad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Resumen de Puerto-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-21_

Los requisitos de puertos de Firewall para un grupo de directores constan de los puertos que se usan para establecer la comunicación con el director desde la interfaz interna del servidor perimetral o la interfaz de conexión interna del proxy inverso. De forma predeterminada, Microsoft Lync Server 2013 espera que se abran los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 desde el proxy inverso al Director, así como al grupo de servidores front-end y al servidor front-end. Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral hasta el director y el grupo de servidores front-end y el servidor front-end. El protocolo SIP utiliza SIP/MTLS/TCP 5061 del servidor perimetral para el grupo de servidores front-end y el servidor front-end. También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end hacia la interfaz interna del servidor perimetral.

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>Protocolos y puertos del Director para la definición de puertos

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol/protocolo/TCP o UDP/puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Director VIP del equilibrador de carga de hardware</p></td>
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Director VIP del equilibrador de carga de hardware</p></td>
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidores front-end</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Dirección</p></td>
<td><p>Servidor front-end o grupo de servidores front-end</p></td>
<td><p>Comunicación entre servidores entre el director HLB VIP y los servidores front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clientes internos</p></td>
<td><p>Director VIP del equilibrador de carga de hardware</p></td>
<td><p>El director proporciona servicios web a clientes internos y externos.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clientes internos</p></td>
<td><p>Director VIP del equilibrador de carga de hardware</p></td>
<td><p>El director proporciona servicios web a clientes internos y externos.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Director VIP del equilibrador de carga de hardware</p></td>
<td><p>Comunicación SIP del servidor perimetral al Director y a los servidores front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección</p></td>
<td><p>Controlador del servicio de registro centralizado (ClsController. exe) o comandos del agente (ClsAgent. exe) y colección de registros</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección</p></td>
<td><p>Controlador del servicio de registro centralizado (ClsController. exe) o comandos del agente (ClsAgent. exe) y colección de registros</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Dirección</p></td>
<td><p>Controlador del servicio de registro centralizado (ClsController. exe) o comandos del agente (ClsAgent. exe) y colección de registros</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

