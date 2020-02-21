---
title: 'Lync Server 2013: requisitos de certificado para movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e1267710405cb9b6c4e64d9cf2e31fb63feddaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Requisitos de certificados para movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-24_

Si implementa la característica de movilidad y admite la detección automática para clientes móviles, debe incluir algunas entradas de nombre alternativo del sujeto en certificados para admitir conexiones seguras desde clientes móviles.

Debe incluir entradas de nombre alternativo del sujeto para la detección automática en los siguientes certificados:

  - Grupo de servidores Director

  - Grupo de servidores front-end

  - Proxy inverso

En esta sección se describen las entradas de nombre alternativo del sujeto necesarias en los certificados para la detección automática.

<div>


> [!NOTE]  
> La reemisión de certificados usando una entidad de certificación interna suele ser un proceso sencillo, pero agregar varias entradas de nombre alternativo del sujeto a certificados públicos usados por el proxy inverso puede resultar caro. Si tiene muchos dominios SIP, lo que provoca que agregar nombres alternativos del sujeto sea caro, puede configurar el proxy inverso para usar HTTP para la solicitud inicial del servicio Detección automática, en lugar de usar HTTPS (la configuración predeterminada). Para obtener más información, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Requisitos de certificado de grupo de directores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL de servicio Detección automática interna</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL de servicio Detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Como alternativa, puede usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisitos de certificado de grupo de servidores front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL de servicio Detección automática interna</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL de servicio Detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Como alternativa, puede usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisitos de certificado (CA pública) de proxy inverso

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo del sujeto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL de servicio Detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Debe asignar este SAN al certificado asignado a la escucha de SSL en el proxy inverso.



</div>

<div>


> [!NOTE]  
> La escucha de proxy inverso tendrá nombres alternativos de sujeto para las direcciones URL de los servicios web externos (por ejemplo, SAN = lyncwebextpool01. contoso. com y dirwebexternal.contoso.com si ha implementado el director opcional).



</div>

</div>

<span> </span>

</div>

</div>

</div>

