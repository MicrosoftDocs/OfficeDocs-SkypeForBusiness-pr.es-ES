---
title: 'Lync Server 2013: Resumen de Puerto-Director único'
description: 'Lync Server 2013: Resumen de Puerto-Director único.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566376"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a>Resumen de Puerto-Director único en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

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
<td><p>Director</p></td>
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director y a los servicios web del servidor front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interfaz interna de proxy inverso</p></td>
<td><p>Director</p></td>
<td><p>Recibida inicialmente por el lado externo del proxy inverso, la comunicación se envía al Director y a los servicios web del servidor front-end</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Director</p></td>
<td><p>Servidor front-end o grupo de servidores front-end</p></td>
<td><p>Comunicación entre servidores entre el director y el servidor front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clientes internos</p></td>
<td><p>Servicios Web de Director</p></td>
<td><p>El director proporciona servicios web a los clientes internos y externos.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clientes internos</p></td>
<td><p>Servicios Web de Director</p></td>
<td><p>El director proporciona servicios web a los clientes internos y externos.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Director</p></td>
<td><p>Comunicación SIP desde el servidor perimetral al Director y el servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Controlador del Servicio de registro centralizado (ClsController.exe) o comandos y colección de registro del agente (ClasAgent.exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Comandos y recopilación de datos de registro del controlador del Servicio de registro centralizado (ClsController.exe) o el agente (ClasAgent.exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Cualquiera</p></td>
<td><p>Interfaz interna del servidor perimetral</p></td>
<td><p>Controlador del Servicio de registro centralizado (ClsController.exe) o comandos y colección de registro del agente (ClasAgent.exe)</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

