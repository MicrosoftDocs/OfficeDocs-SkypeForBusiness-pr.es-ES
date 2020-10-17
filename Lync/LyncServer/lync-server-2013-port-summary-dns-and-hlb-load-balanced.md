---
title: 'Lync Server 2013: Resumen de Puerto-carga equilibrada DNS y HLB'
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
ms.openlocfilehash: b6ba03a73538426b9c820388f65e728c36881148
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527947"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Resumen de Puerto-carga equilibrada DNS y HLB en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Los requisitos de puerto de Firewall para un solo Director constan de los puertos que se usan para establecer la comunicación con el director desde la interfaz interna o la red interna del proxy inverso. De forma predeterminada, Microsoft Lync Server 2013 espera que se abran los puertos HTTP/TCP 8080 y HTTPS/TCP 4443 desde el proxy inverso al Director, así como al grupo de servidores front-end y al servidor front-end. Además, debe haber comunicación del Protocolo de inicio de sesión (SIP) desde la interfaz interna del servidor perimetral hasta el director y el grupo de servidores front-end y el servidor front-end. El protocolo SIP utiliza SIP/MTLS/TCP 5061 del servidor perimetral para el grupo de servidores front-end y el servidor front-end. También se debe crear una regla que permita la comunicación SIP/MTLS/TCP 5061 desde el director, el grupo de servidores front-end y el servidor front-end hacia la interfaz interna del servidor perimetral.

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
<th>Rol/Protocolo/TCP o UDP/Puerto</th>
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
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios web del servidor front-end.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Director VIP del equilibrador de carga de hardware</p></td>
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director HLB VIP y los servicios web del servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Grupo de servidores front-end o servidor front-end</p></td>
<td><p>Comunicación entre servidores entre el director HLB VIP y el servidor front-end o el servidor front-end.</p></td>
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
<td><p>Director</p></td>
<td><p>Comunicación SIP del servidor perimetral al Director, así como los servidores front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Director</p></td>
<td><p>Controlador del servicio de registro centralizado (ClsController.exe) o comandos del agente (ClsAgent.exe) y colección de registros</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

