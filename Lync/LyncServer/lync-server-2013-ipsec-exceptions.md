---
title: Excepciones IPsec de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Excepciones de IPsec en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-27_

En el caso de redes empresariales en las que se ha implementado la seguridad de protocolo de Internet (consulte IETF RFC 4301-4309), debe deshabilitarse IPsec en el rango de puertos que se usan para la entrega de video de audio, vídeo y panorámica. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios por la negociación de IPsec.

En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.

### <a name="recommended-ipsec-exceptions"></a>Excepciones de IPsec recomendadas

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de regla</th>
<th>IP de origen</th>
<th>IP de destino</th>
<th>Protocolo</th>
<th>Puerto de origen</th>
<th>Puerto de destino</th>
<th>Requisito de autenticación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor perimetral A/V interno entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral A/V interno</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Servidor perimetral A/V externo entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor perimetral A/V externo</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Servidor perimetral A/V interno saliente</p></td>
<td><p>Servidor perimetral A/V interno</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP &amp; UDP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Servidor perimetral A/V externo saliente</p></td>
<td><p>Servidor perimetral A/V externo</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Servidor de mediación entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidores</p>
<p>de mediación</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Servidor de mediación saliente</p></td>
<td><p>Servidores</p>
<p>de mediación</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Operador de conferencia entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidor front-end que ejecuta operador de conferencia</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Operador de conferencia saliente</p></td>
<td><p>Servidor front-end que ejecuta operador de conferencia</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Servidor de conferencia A/V entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidores front-end</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Salida de conferencia A/V</p></td>
<td><p>Servidores front-end</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Exchange entrante</p></td>
<td><p>Cualquiera</p></td>
<td><p>Mensajería unificada de Exchange</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Servidores de aplicaciones compartidas entrantes</p></td>
<td><p>Cualquiera</p></td>
<td><p>Servidores de aplicaciones compartidas</p></td>
<td><p>TCP</p></td>
<td><p>Cualquiera</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Servidor de aplicaciones compartidas saliente</p></td>
<td><p>Servidores de aplicaciones compartidas</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="even">
<td><p>Exchange saliente</p></td>
<td><p>Mensajería unificada de Exchange</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP y TCP</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>Cualquiera </p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP</p></td>
<td><p>Intervalo de puertos de medios especificado</p></td>
<td><p>Cualquiera</p></td>
<td><p>No autenticar</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

