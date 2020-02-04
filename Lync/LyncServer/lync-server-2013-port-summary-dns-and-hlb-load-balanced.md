---
title: 'Lync Server 2013: Resumen de puerto - Carga equilibrada DNS y HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb594057977fbe39f6be6a9a9c678806d7e2d8dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Resumen de puerto - Carga equilibrada DNS y HLB en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Los requisitos del puerto de Firewall para un único Director son los puertos que se usan para establecer comunicación con el director desde la interfaz interna o la red interna del proxy inverso. Microsoft Lync Server 2013 espera de forma predeterminada que los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 se abran desde el proxy inverso al Director, así como el servidor front-end y el servidor front-end. Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral al Director y al grupo de servidores front-end y front-end. El protocolo SIP usa SIP/MTLS/TCP 5061 del servidor perimetral al grupo front-end y al servidor front-end. También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end a la interfaz interna del servidor perimetral.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Puertos y protocolos de un solo Director para definiciones de Firewall

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Función/protocolo/TCP o UDP/puerto</th>
<th>Dirección IP de origen</th>
<th>Dirección IP de destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interfaz interna de proxy invertida</p></td>
<td><p>Director VIP de equilibrador de carga de hardware</p></td>
<td><p>Inicialmente recibido por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidor front-end.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaz interna de proxy invertida</p></td>
<td><p>Director VIP de equilibrador de carga de hardware</p></td>
<td><p>Inicialmente recibido por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios Web de servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Grupo de servidores front-end o servidor front-end</p></td>
<td><p>Comunicación entre servidores entre el director HLB VIP y el servidor front-end o front-end.</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clientes internos</p></td>
<td><p>Director VIP de equilibrador de carga de hardware</p></td>
<td><p>El director proporciona servicios web a clientes externos y internos.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clientes internos</p></td>
<td><p>Director VIP de equilibrador de carga de hardware</p></td>
<td><p>El director proporciona servicios web a clientes externos y internos.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interfaz interna de Edge Server</p></td>
<td><p>Director</p></td>
<td><p>Comunicación SIP desde el servidor perimetral al Director, así como a los servidores front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Comandos del controlador de registro centralizado (ClsController. exe) o agente (ClsAgent. exe) y recopilación de registros</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

