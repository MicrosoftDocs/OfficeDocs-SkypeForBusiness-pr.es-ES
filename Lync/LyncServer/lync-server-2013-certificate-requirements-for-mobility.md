---
title: 'Lync Server 2013: Requisitos de certificado para movilidad'
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
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Requisitos de certificado para movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-24_

Si implementa la característica de movilidad y admite el descubrimiento automático para clientes móviles, debe incluir determinadas entradas de nombre alternativo de sujeto en certificados para admitir conexiones seguras desde los clientes móviles.

Debe incluir las entradas de nombre alternativo de asunto para el descubrimiento automático en los siguientes certificados:

  - Grupo de directores

  - Grupo de servidores front-end

  - Proxy inverso

En esta sección se describen las entradas de nombre alternativo de asunto necesarias en los certificados para la detección automática.

<div>


> [!NOTE]  
> La reemisión de certificados mediante una entidad emisora de certificados interna suele ser un proceso simple, pero la adición de varias entradas de nombre alternativo de asunto a certificados públicos que usa el proxy inverso puede ser costosa. Si tiene muchos dominios SIP, lo que hace que la adición de nombres alternativos del sujeto sea muy costosa, puede configurar el proxy inverso para usar HTTP en la solicitud de servicio de detección automática inicial, en lugar de usar HTTPS (la configuración predeterminada). Para obtener más información, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">requisitos técnicos para la movilidad en Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Requisitos de certificados del grupo de directores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo de asunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dirección URL del servicio de detección automática interna</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>Dirección URL del servicio de detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> También puede usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisitos del certificado del grupo de servidores front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo de asunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dirección URL del servicio de detección automática interna</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>Dirección URL del servicio de detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> También puede usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisitos de los certificados de proxy inverso (CA pública)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Entrada de nombre alternativo de asunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dirección URL del servicio de detección automática externa</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Asigna este SAN al certificado asignado a la escucha SSL en el proxy inverso.



</div>

<div>


> [!NOTE]  
> Su agente de escucha de proxy inverso tendrá nombres alternativos de asunto para las URL de los servicios web externos (por ejemplo, SAN = lyncwebextpool01. contoso. com y dirwebexternal.contoso.com si ha implementado el director opcional).



</div>

</div>

<span> </span>

</div>

</div>

</div>

